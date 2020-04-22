<template>
  <div class="side-filter">
    <div class="filter-link">
      {{ name }}
    </div>
  </div>
</template>

<script lang="ts">
import { Component, Prop, Vue } from "vue-property-decorator";

@Component
export default class SideFilter extends Vue {
  @Prop() name!: string;
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped lang="scss">
.filter-link {
  cursor: pointer;
  max-width: 80px;
  &:hover{
    background: #31302e;
    color: #FFFFFF;
  }
}
h3 {
  margin: 40px 0 0;
}
ul {
  list-style-type: none;
  padding: 0;
}
li {
  display: inline-block;
  margin: 0 10px;
}
a {
  color: #31302e;
}
</style>
