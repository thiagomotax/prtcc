<template>
  <v-container class="rounded mb-5">
    <h3>{{ id }}. {{ text }}</h3>
    <ul v-if="infos">
      <li v-for="info in infos">
        {{ info }}
      </li>
    </ul>
  </v-container>
</template>

<script>
export default {
  name: "QuestionHeader",
  props: {
    id: String,
    text: String,
    infos: Array,
  },
};
</script>

<style lang="scss" scoped>
</style>