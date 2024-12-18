<template>
  <header>
    <div id="nav">
      <nav>
        <RouterLink to="/">Home</RouterLink>
        <RouterLink to="/about">About</RouterLink>
        <router-link
          :to="destination.slug"
          v-for="destination in destinations"
          :key="destination.id"
          >{{ destination.name }}</router-link
        >
      </nav>
    </div>
  </header>

  <div class="container">
    <RouterView />
  </div>
</template>

<script>
import { RouterLink, RouterView } from "vue-router";
import sourceData from "@/data.json";
export default {
  data() {
    return {
      destinations: sourceData.destinations,
    };
  },
};
</script>
