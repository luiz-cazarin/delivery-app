<template>
  <q-layout view="hHh lpR fFf">
    <!-- header -->

    <!-- body -->
    <q-page-container>
      <router-view />
    </q-page-container>
    <!-- footer menu -->
    <q-footer class="menu">
      <q-list class="list">
        <template v-for="item in items" :key="item.icon">
          <q-item clickable>
            <q-item-section>
              <q-btn
                flat
                size="lg"
                color="grey"
                :icon="item.icon"
                :to="item.link"
              />
            </q-item-section>
          </q-item>
        </template>
      </q-list>
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
      menuList: [
        {
          icon: "inbox",
          label: "Inbox",
        },
        {
          icon: "send",
          label: "Outbox",
        },
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
  .list {
    justify-content: space-evenly;
    list-style: none;
    display: flex;
    padding: 0.2rem 0px !important;
    margin: 0px !important;
    .icon {
      color: #939393;
    }
  }
}
</style>
