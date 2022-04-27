<template>
  <div class="container">
    <div class="search-input-container">
      <input
        :placeholder="placeholder"
        type="text"
        @input="onChange"
        v-model="search"
        @keydown.down="onArrowDown"
        @keydown.up="onArrowUp"
        @keydown.enter="onEnter"
      />
      <img src="@/assets/icon/black/ic_search.png" />
    </div>
    <ul id="search-results" v-show="isOpen" class="search-results">
      <li class="loading" v-if="isLoading">Loading results...</li>
      <li class="loading" v-if="!isLoading && !results.length">No results!</li>
      <li
        v-else
        v-for="(result, i) in results"
        :key="i"
        @click="setResult(result)"
        class="search-result-item"
        :class="{ 'is-active': i === arrowCounter }"
      >
        {{ result }}
      </li>
    </ul>
  </div>
</template>

<script>
import { Options, Vue } from "vue-class-component";
import axios from "axios";

@Options({
  props: {
    placeholder: {
      type: String,
      required: false,
      default: () => "",
    },
  },
  data() {
    return {
      isOpen: false,
      results: [],
      search: "",
      isLoading: false,
      arrowCounter: -1,
      axiosSource: null,
      apiUrl: "https://swapi.dev/api/people/",
    };
  },
  watch: {
    items: function (value, oldValue) {
      if (value.length !== oldValue.length) {
        this.results = value;
        this.isLoading = false;
      }
    },
  },
  mounted() {
    document.addEventListener("click", this.handleClickOutside);
  },
  unmounted() {
    document.removeEventListener("click", this.handleClickOutside);
  },
  methods: {
    setResult(result) {
      this.search = result;
      this.isOpen = false;
    },
    filterResults() {
      this.axiosSource = axios.CancelToken.source();
      axios
        .get(this.apiUrl, {
          cancelToken: this.axiosSource.token,
          params: { search: this.search },
        })
        .then((response) => {
          this.results = response.data.results.map((res) => res.name);
          this.isLoading = false;
        })
        .catch((e) => {
          console.log(e);
        });
    },
    onChange() {
      if (this.axiosSource) this.axiosSource.cancel();
      this.isLoading = true;
      this.filterResults();
      this.isOpen = true;
    },
    handleClickOutside(event) {
      if (!this.$el.contains(event.target)) {
        this.isOpen = false;
        this.arrowCounter = -1;
      }
    },
    onArrowDown() {
      if (this.arrowCounter < this.results.length) {
        this.arrowCounter = this.arrowCounter + 1;
      }
    },
    onArrowUp() {
      if (this.arrowCounter > 0) {
        this.arrowCounter = this.arrowCounter - 1;
      }
    },
    onEnter() {
      this.search = this.results[this.arrowCounter];
      this.isOpen = false;
      this.arrowCounter = -1;
    },
  },
})
export default class SearchInput extends Vue {}
</script>

<style lang="scss" scoped>
.container {
  width: 100%;
  align-items: normal;

  .search-input-container {
    display: flex;
    flex-direction: row;
    background-color: var(--white);
    border-radius: 0.5rem;
    align-items: center;
    margin: 0.5rem 0;

    @media screen and (max-width: 600px) {
      margin: 1rem;
    }

    input {
      margin: 1rem;
      border: 0;
      width: 100%;
      outline: none;
    }

    img {
      width: 1.5rem;
      height: 1.5rem;
      margin-right: 1rem;
    }
  }

  .search-results {
    padding: 1rem;
    margin: 0;
    border: 1px solid #eeeeee;
    height: 120px;
    background-color: var(--white);
    overflow: auto;
    border-bottom-right-radius: 0.5rem;
    border-bottom-left-radius: 0.5rem;

    li {
      list-style: none;

      &.search-result-item {
        text-align: left;
        padding: 4px 2px;
        cursor: pointer;
      }
      &.search-result-item.is-active,
      &.search-result-item:hover {
        background-color: #4aae9b;
        color: var(--white);
      }
    }
  }
}
</style>
