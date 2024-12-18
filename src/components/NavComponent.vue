<template>
  <div id="nav">
    <nav>
      <RouterLink to="/">Home</RouterLink>
      <RouterLink to="/about">About</RouterLink>
      <router-link
        v-for="destination in destinations"
        :to="{ name: 'destination.show', params: { id: destination.id } }"
        :key="destination.id"
      >
        {{ destination.name }}
      </router-link>
    </nav>
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
