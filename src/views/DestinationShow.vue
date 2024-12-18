<template>
  <section class="destination">
    <h1>{{ destination.name }}</h1>
    <div class="destination-details">
      <img :src="`/images/${destination.image}`" :alt="destination.name" />
      <p>{{ destination.description }}</p>
    </div>
  </section>

  <section>
    <div class="home">
      <h1>All Destinations</h1>
      <div class="destinations">
        <router-link
          v-for="destination in destinations"
          :to="`/destination/${destination.id}`"
          :key="destination.id"
        >
          <h2>{{ destination.name }}</h2>
          <img :src="`/images/${destination.image}`" :alt="destination.name" />
        </router-link>
      </div>
    </div>
  </section>
</template>

<script>
import sourceData from "@/data.json";
export default {
  data() {
    return {
      destinations: sourceData.destinations,
    };
  },

  computed: {
    destinationId() {
      return parseInt(this.$route.params.id);
    },

    destination() {
      return sourceData.destinations.find(
        (destination) => destination.id === this.destinationId
      );
    },
  },
};
</script>
