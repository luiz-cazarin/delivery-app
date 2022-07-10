<template>
  <q-header class="bg-white">
    <q-toolbar class="q-pt-xl q-pb-sm">
      <q-btn color="red" flat round dense icon="chevron_left" to="/login" />
      <q-space />
      <q-title class="text-black text-bold">{{ "Home" }}</q-title>
      <q-space style="margin-right: 34px" />
    </q-toolbar>
  </q-header>
  <q-page>
    <div class="body">
      <div class="header-text">
        <p class="t1">Welcome</p>
        <p class="t2">Special for you</p>
      </div>

      <q-dialog v-model="dialog" position="bottom" maximized>
        <dialog-item></dialog-item>
      </q-dialog>

      <div class="list-category q-px-md">
        <q-chip
          v-for="c in category"
          :key="c.title"
          :color="!c.active ? 'grey-8' : 'red'"
          outline
          clickable
          @click="onClick(c)"
        >
          {{ c.title }}
        </q-chip>
      </div>

      <div class="row inline wrap justify-between body-content">
        <card-item
          v-for="item in items"
          :key="item.id"
          :title="item.title"
          :img="item.img"
          :price="item.price.toFixed(2)"
          @click="open('bottom')"
        ></card-item>
      </div>
    </div>
  </q-page>
</template>

<script>
import CardItem from "../components/CardItem.vue";
import { ref } from "vue";
import DialogItem from "src/components/DialogItem.vue";

export default {
  components: {
    CardItem,
    DialogItem,
  },
  setup() {
    const dialog = ref(false);
    const position = ref("top");
    return {
      dialog,
      position,
      items: [
        {
          id: 0,
          title: "Pizza",
          img: "https://s.calendarr.com/upload/datas/pi/zz/pizza_c.jpg?auto_optimize=low&width=640",
          price: 23.0,
        },
        {
          id: 1,
          title: "Pizza",
          img: "https://cdn.quasar.dev/img/chicken-salad.jpg",
          price: 23.0,
        },
        {
          id: 1,
          title: "Pizza",
          img: "https://cdn.quasar.dev/img/chicken-salad.jpg",
          price: 23.0,
        },
        {
          id: 1,
          title: "Pizza",
          img: "https://cdn.quasar.dev/img/chicken-salad.jpg",
          price: 23.0,
        },
      ],
      category: [
        {
          title: "Salgado",
          active: true,
        },
        {
          title: "Bebidas",
          active: false,
        },
        {
          title: "Combo",
          active: false,
        },
        {
          title: "Doce",
          active: false,
        },
      ],
      shape: ref(["line"]),
      open() {
        dialog.value = true;
      },
      onClick(element) {
        console.log(element);
      },
    };
  },
  computed: {
    styleCategory(el) {
      console.log(el);
      return "grey-8";
    },
  },
  methods() {},
};
</script>

<style lang="scss" scoped>
.body {
  height: 90vh;
  .header-text {
    padding: 0.5rem 1.5rem;
    font-family: "Segoe UI", Tahoma, Geneva, Verdana, sans-serif;
    .t1 {
      margin: 0;
      padding: 0;
      font-weight: 600;
      color: #b6b6b6b6;
      font-size: 14px;
    }
    .t2 {
      margin: 0;
      padding: 0;
      font-size: 16px;
      font-weight: bold;
      color: #de2e2e;
    }
  }
  .body-content {
    row-gap: 0.5rem;
    padding: 0.5rem;
    width: 100%;
    margin-bottom: 80px;
  }
  .list-category {
    overflow-x: auto;
    overflow-y: hidden;
    height: auto;
    white-space: nowrap;
    padding: 0.5rem 1rem;
  }
  ::-webkit-scrollbar {
    height: 3px;
  }
}
</style>
