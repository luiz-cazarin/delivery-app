<template>
  <q-layout view="hHh lpR fFf">
    <!-- header -->
    <q-header class="bg-white">
      <q-toolbar class="q-pt-xl q-pb-sm">
        <q-btn color="red" flat round dense icon="chevron_left" />
        <q-space />
        <q-title class="text-black text-bold">{{ "Home" }}</q-title>
        <q-space />
      </q-toolbar>
    </q-header>
    <!-- body -->
    <q-page-container>
      <router-view />
    </q-page-container>
    <!-- footer menu -->
    <q-footer class="menu">
      <ul>
        <li v-for="item in items" :key="item.link">
          <q-icon class="icon" size="md" :name="item.icon"></q-icon>
        </li>
      </ul>
    </q-footer>
  </q-layout>
</template>

<script>
export default {
  data() {
    return {
      items: [
        { icon: "home", link: "https://awesome.quasar.dev" },
        { icon: "search", link: "https://awesome.quasar.dev" },
        { icon: "local_grocery_store", link: "https://awesome.quasar.dev" },
        { icon: "person_outline", link: "https://awesome.quasar.dev" },
      ],
    };
  },
};
</script>

<style lang="scss" scoped>
.menu {
  background: rgb(255, 255, 255);
  padding: 0.2rem 0;
  box-shadow: 0px -1px 8px rgba(0, 0, 0, 0.178);
  ul {
    justify-content: space-around;
    list-style: none;
    display: flex;
    .icon {
      color: #939393;
    }
  }
}
</style>
