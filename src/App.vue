<template>
  <header>
    <NavComponent />
  </header>

  <div class="container">
    <RouterView />
  </div>
</template>

<script>
import { RouterLink, RouterView } from "vue-router";
import NavComponent from "@/components/NavComponent.vue";

export default {
  components: {
    NavComponent,
  },
};
</script>
