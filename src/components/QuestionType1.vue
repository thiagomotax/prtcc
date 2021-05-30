<template>
  <v-row class="align-center pb-0 mb-0" :style="{ 'background-color': color}">
    <v-col cols="12" md="4" xs="12">{{ number }}. {{ text }}</v-col>
    <v-col cols="12" md="4" xs="12">
      <v-radio-group row>
        <v-radio label="1"></v-radio>
        <v-radio label="2"></v-radio>
        <v-radio label="3"></v-radio>
        <v-radio label="4"></v-radio>
        <v-radio label="5"></v-radio>
      </v-radio-group>
    </v-col>
    <v-col cols="12" md="4" xs="12" class="d-inline-flex">
      <v-text-field class="pr-2"></v-text-field>
      <v-text-field></v-text-field>
    </v-col>
  </v-row>
</template>

<script>
export default {
    name: 'QuestionType1',
    props: {
        text: String,
        number: Number,
        color: String
    }
};
</script>

<style lang="scss" scoped>
</style>