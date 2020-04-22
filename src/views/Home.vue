<template>
  <div class="home">
    <HeadBar msg="WELCOME TO ISA TEST SHOP" />
        <h1> {{ category.name }} </h1>
    <CategoryList/>
  </div>
</template>

<script lang="ts">
import { Component, Vue } from "vue-property-decorator";
import HeadBar from "../components/HeadBar.vue";
import CategoryList from "../components/CategoryList.vue";
import CategoryModel from "../models/CategoryModel.vue";

@Component({
  components: {
    HeadBar,
    CategoryList,
    CategoryModel
  }
})
export default class Home extends Vue {
  model = new CategoryModel();
  category: unknown = this.model.getCategory();

}
</script>
<style lang="scss">
</style>
