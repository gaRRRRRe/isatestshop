<template>
  <div>
    <div class="product">
      <ProductComponentView :title="$route.fullPath.split('/')[2]" />
    </div>
  </div>
</template>

<script lang="ts">
import { Vue, Component } from "vue-property-decorator";
import ProductComponentView from "../components/ProductComponentView.vue";

@Component({
  components: {
    ProductComponentView
  }
})
export default class Game extends Vue {

}
</script>
