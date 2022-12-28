<template>
  <div class="home">
    <DribbleApp />
  </div>
</template>

<script lang="ts">
import Vue from "vue";
import DribbleApp from "@/components/DribbleApp.vue";

export default Vue.extend({
  name: "HomeView",
  components: {
    DribbleApp,
  },
});
</script>
