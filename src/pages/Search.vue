<template>
  <q-header class="bg-white">
    <q-toolbar class="q-pt-xl q-pb-sm">
      <q-btn color="red" flat round dense icon="chevron_left" to="/login" />
      <q-space />
      <q-title class="text-black text-bold">{{ "Search" }}</q-title>
      <q-space style="margin-right: 34px" />
    </q-toolbar>
  </q-header>
  <q-page>
    <q-input color="grey-3" class="q-pa-md" outlined>
      <template v-slot:prepend>
        <q-icon color="grey-5" name="search" />
      </template>
    </q-input>
  </q-page>
</template>

<script>
import { defineComponent } from "vue";
export default defineComponent({
  name: "search-page",
});
</script>

<style></style>
