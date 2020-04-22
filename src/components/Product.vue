<template>
  <div class="product">
    <router-link :to="'/product/' + name" :url="url"> {{ name }}</router-link>
    <span> {{ price }}</span>
    <span> {{ brand }}</span>
  </div>
</template>

<script lang="ts">
import { Prop, Vue, Component } from "vue-property-decorator";

@Component
export default class Product extends Vue {
  @Prop() name!: string;
  @Prop() price!: string;
  @Prop() brand!: string;
  @Prop() url!: string;
}
</script>
<style lang="scss">
a:link,
a:visited {
  color: #444343;
  text-decoration: none;
}
</style>
<!-- Add "scoped" attribute to limit CSS to this component only -->
<!-- <style scoped lang="scss"></style> -->
