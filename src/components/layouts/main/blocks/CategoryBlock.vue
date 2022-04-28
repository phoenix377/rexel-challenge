<template>
  <div class="category-block">
    <ul>
      <li v-for="(category, i) in categories" :key="i">
        <category-item
          :type="category.type"
          :label="category.title"
          :leftIcon="category.leftIcon"
          :rightIcon="category.rightIcon"
        />
      </li>
    </ul>
  </div>
</template>

<script lang="ts">
import { Options, Vue } from "vue-class-component";
import CategoryItem from "@/components/CategoryItem.vue";
import { categories } from "@/assets/data/categories";

@Options({
  components: {
    CategoryItem,
  },
  data() {
    return { categories };
  },
  methods: {
    getCategories: function () {
      this.categories = categories;
    },
  },
  mounted: function () {
    this.getCategories();
  },
})
export default class CategoryBlock extends Vue {}
</script>

<style lang="scss" scoped>
.category-block {
  background-color: var(--white);

  ul {
    padding: 0 1rem;
    margin: 0px;
    list-style-type: none;

    @media screen and (min-width: 600px) {
      display: flex;
      flex-wrap: wrap;
      padding: 0;
    }

    li {
      border-bottom: 1px solid #ccc;
      @media screen and (min-width: 600px) {
        width: 33%;
        border: 1px solid #ccc;

        &:nth-of-type(3n + 4) {
          width: calc(34% - 6px);
        }
      }

      &:first-child {
        font-weight: bold;
        font-size: 1.2rem;
        padding-bottom: 0.5rem;

        @media screen and (min-width: 600px) {
          width: 100%;
          border: none;
        }
      }

      &:last-child {
        border-bottom: none;

        @media screen and (min-width: 600px) {
          border: 1px solid #ccc;
        }
      }
    }
  }
}
</style>
