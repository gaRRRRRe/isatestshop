<template>
  <div>
    <div class="productview">
      <h1>{{ title }}</h1>
    </div>
  </div>
</template>

<script lang="ts">
import { Prop, Vue, Component } from "vue-property-decorator";

@Component
export default class ProductComponentView extends Vue {
  @Prop() title!: string;
  @Prop() url!: string;
}
</script>
