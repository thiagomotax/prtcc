<template>
  <div>
    <v-tabs v-model="tab" background-color="transparent" color="basil" grow>
      <v-tab key="form1"> Form 1 </v-tab>
      <v-tab key="form2"> Form 2 </v-tab>
    </v-tabs>

    <v-tabs-items v-model="tab">
      <v-tab-item key="form1">
        <v-card color="basil" flat>
          <FormPage1 />
        </v-card>
      </v-tab-item>

      <v-tab-item key="form2">
        <v-card color="basil" flat>
        </v-card>
      </v-tab-item>
    </v-tabs-items>
  </div>
</template>

<script>
import FormPage1 from "./FormPage1";

export default {
  components: {
    FormPage1,
  },
  data() {
    return {
      tab: null,
    };
  },
};
</script>

<style lang="scss" scoped>
</style>