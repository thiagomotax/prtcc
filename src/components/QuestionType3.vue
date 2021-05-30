<template>
  <v-container>
    <!--class="mediumPurple" -->
    <v-row class="align-center pa-n10">
      <v-col cols="12" sm="6" md="1">
        <h4>{{ id }}</h4>
      </v-col>

      <v-col cols="12" sm="6" md="4">
        <p>{{ text }}</p>
      </v-col>

      <v-col cols="12" sm="6" md="1">
        <p>{{ exampleNumber }}</p>
      </v-col>

      <v-col cols="12" sm="6" md="2">
        <v-text-field dense label=""></v-text-field>
      </v-col>

      <v-col cols="12" sm="6" md="2">
        <v-text-field dense label=""></v-text-field>
      </v-col>

      <v-col cols="12" sm="6" md="2">
        <v-text-field dense label=""></v-text-field>
      </v-col>
    </v-row>
    <!-- se finalcomment =! de "" mostrar essa parte -->

    <v-row v-if="finalComment && finalComment != ''">
      <v-col cols="12" sm="6" md="12">
        <p>{{ finalComment }}</p>
      </v-col>
    </v-row>
  </v-container>
</template>

<script>
export default {
  name: "QuestionType3",
  props: {
    id: {
      type: String,
    },
    text: {
      type: String,
    },
    exampleNumber: {
      type: String,
    },
    finalComment: {
      type: String,
    },
  },
};
</script>

<style lang="scss" scoped>
.mediumPurple {
  background-color: rgb(205, 192, 218);
}
</style>