<template>
  <div>
    <px-assets-table v-bind:assets="assets"></px-assets-table>
  </div>
</template>

<script>
import api from "@/api";
import PxAssetsTable from "@/components/PxAssetsTable.vue";
export default {
  // eslint-disable-next-line vue/multi-word-component-names
  name: "Home",
  components: { PxAssetsTable },

  data() {
    return {
      assets: [],
    };
  },

  created() {
    api.getAssets().then((assets) => (this.assets = assets));
  },
};
</script>
