<template>
  <section>
    <h1>Experiences</h1>
    <h2>{{ experience.name }}</h2>
    <div class="experience-details">
      <img
        :src="require(`@/assets/${experience.image}`)"
        :alt="experience.name"
      />
      <p>{{ experience.description }}</p>
    </div>
  </section>
</template>
<script>
import store from "@/store/store.js";
export default {
  props: {
    slug: {
      typs: String,
      required: true,
    },
    experienceSlug: {
      type: String,
      required: true,
    },
  },
  computed: {
    destination: function () {
      return store.destinations.find(
        (destination) => destination.slug === this.slug
      );
    },
    experience: function () {
      return this.destination.experiences.find(
        (experience) => experience.slug === this.experienceSlug
      );
    },
  },
};
</script>
<style scoped>
section {
  height: auto;
  width: 100%;
  max-height: 400px;
}
.experience-details {
  display: flex;
  justify-content: center;
}
p {
  margin: 0 40px;
  font-size: 20px;
  text-align: left;
}
</style>
