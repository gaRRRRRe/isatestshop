<script lang="ts">
import { Vue } from "vue-property-decorator";
export default class CategoryModel extends Vue {
  category: unknown = {
        "name": "Kleidung",
        "breadcrumb": ["Damen", "Kleidung"]
    };

  public getCategory() {
    return this.category;
  }
}
</script>
