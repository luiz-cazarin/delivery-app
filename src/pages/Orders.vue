<template>
  <q-header class="bg-white">
    <q-toolbar class="q-pt-xl q-pb-sm">
      <q-btn color="red" flat round dense icon="chevron_left" to="/" />
      <q-space />
      <q-title class="text-black text-bold">{{ "Orders" }}</q-title>
      <q-space style="margin-right: 34px" />
    </q-toolbar>
  </q-header>
  <q-page></q-page>
</template>

<script>
import { defineComponent } from "vue";

export default defineComponent({
  name: "orders-page",
});
</script>

<style></style>
