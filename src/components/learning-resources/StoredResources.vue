<template>
  <ul class="font-robato">
    <learning-resource
      v-for="res in resources"
      :id="res.id"
      :key="res.id"
      :title="res.title"
      :description="res.description"
      :link="res.link"
    >
    </learning-resource>
  </ul>
</template>

<script>
import LearningResource from "./LearningResource.vue";
export default {
  components: {
    LearningResource,
  },
  inject: ["resources"],
};
</script>
