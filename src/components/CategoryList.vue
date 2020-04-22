<template>
  <div class="category-list">
    <SideFilter class="color-filter"
      v-for="filter in colorFilter"
      :key="filter"
      :name="filter"
      @click.native="filterList(filter)"
      >
    </SideFilter>
    <br>
    <SideFilter name="highprice" key="highprice" @click.native="sortPricehigh()" />
    <SideFilter name="lowprice" key="lowprice" @click.native="sortPricelow()" />
    <Product
      v-for="product in products"
      :key="product.name"
      :name="product.name"
      :price="product.price"
      :brand="product.brand"
      :url="product.image"
    >
    </Product>
  </div>
</template>

<script lang="ts">
import { Component, Vue, Prop } from "vue-property-decorator";
import Product from "./Product.vue";
import SideFilter from "./SideFilter.vue";
import ProductsModel from "../models/ProductsModel.vue";

@Component({
  components: {
    Product,
    SideFilter   
  }
})
export default class CategoryList extends Vue {
  @Prop() boxtitle!: string;
  model = new ProductsModel();
  // eslint-disable-next-line @typescript-eslint/no-explicit-any
  products: any[] = this.model.getAvailableProducts(); // use axios async
  // eslint-disable-next-line @typescript-eslint/no-explicit-any
  colorFilter: any[] = this.model.getAvailableColors();
  filtertest = "none";

  // eslint-disable-next-line @typescript-eslint/no-explicit-any
  filterList(filter: any) {
    if(filter == "none"){
      this.products = this.model.getAvailableProducts();
    } else {
      this.products = this.model.getAvailableProducts().filter(product => product.color == filter);
    }
  }

  sortPricelow(){
    const sortedList = this.products.sort(function(a, b){return a.price-b.price});
    this.products = sortedList;
  }
  sortPricehigh(){
    const sortedList = this.products.sort(function(a, b){return b.price-a.price});
    this.products = sortedList;
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped lang="scss">
.product {
  border: 2px #413f3d solid;
  border-radius: 10px;
  width: 10%;
  min-width: 162px;
  height: 162px;
  line-height: 62px;
  display: inline-block;
  margin: 4px;
  text-overflow: ellipsis;
  overflow: hidden;
  text-align: center;
  color: #333333;
  &:hover {
    background-color: #616161;
    color: #bdbdbd;
    transition: 0.2s;
  }
}
</style>
