<template>
  <q-layout view="hHh lpR fFf">
    <!-- header -->

    <!-- body -->
    <q-page-container>
      <router-view />
    </q-page-container>
    <!-- footer menu -->
    <q-footer class="menu">
      <ul>
        <li v-for="item in items" :key="item.link">
          <q-btn class="icon" flat size="lg" :icon="item.icon" :to="item.link">
          </q-btn>
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
        { icon: "home", link: "/" },
        { icon: "search", link: "/search" },
        { icon: "local_grocery_store", link: "/orders" },
        { icon: "person_outline", link: "/profile" },
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
    padding: 0.5rem 0px !important;
    margin: 0px !important;
    .icon {
      color: #939393;
    }
  }
}
</style>
