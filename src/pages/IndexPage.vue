<template>
  <q-header class="bg-white">
    <q-toolbar class="q-pt-xl q-pb-sm">
      <q-btn color="red" flat round dense icon="chevron_left" to="/login" />
      <q-space />
      <q-title class="text-black text-bold">{{ "Home" }}</q-title>
      <q-space />
      <q-btn color="red" flat round dense to="/login" />
    </q-toolbar>
  </q-header>
  <q-page>
    <div class="body">
      <div class="header-text">
        <p class="t1">Welcome</p>
        <p class="t2">Special for you</p>
      </div>

      <q-dialog v-model="dialog" position="bottom" maximized>
        <q-card class="dialog">
          <q-card-section class="body-iphone">
            <div class="iphone"></div>
          </q-card-section>
          <q-card-section class="q-py-none">
            <q-img
              src="https://cdn.quasar.dev/img/chicken-salad.jpg"
              class="img-card-section"
            />
          </q-card-section>
          <q-card-section>
            <div class="text-h6">Pizza grande</div>
            <div class="text-card-section">
              Se liga que essa deliciosa novidade vem para saciar a sua fome,
              vem comigo de pizza grande com borda recheada
            </div>
          </q-card-section>
          <q-card-section>
            <div
              class="fufull-width row no-wrap justify-between items-center content-center"
            >
              <div class="counter">
                <q-btn round color="grey-4" class="btn-resize" dense>-</q-btn>
                <div class="counter-num">0</div>
                <q-btn round color="primary" class="btn-resize" dense>+</q-btn>
              </div>
              <div class="price text-positive">R$ 38,00</div>
            </div>
          </q-card-section>
          <q-card-section class="bg-grey-3">
            <div class="text-subtitle2 text-grey-8">
              Deseja Adicionar algum item?
            </div>
            <div class="text-card-section-2">Escolha pelomenos uma opção.</div>
          </q-card-section>
          <q-card-section
            v-for="i in items"
            :key="i.id"
            class="fufull-width row no-wrap justify-between"
          >
            <div>
              <div class="text-subtitle2 text-grey-8">Adicionar calabresa</div>
              <div class="text-subtitle2 text-grey-8">+ R$ 8,00</div>
            </div>
            <div class="text-card-section-2">
              <q-checkbox size="md" v-model="shape" val="md" />
            </div>
          </q-card-section>
          <q-card-section class="full-width row justify-center">
            <q-btn class="btn-buy" color="primary">Adicionar ao carrinho</q-btn>
          </q-card-section>
        </q-card>
      </q-dialog>

      <div class="list-category q-px-md">
        <q-chip
          v-for="c in category"
          :key="c.title"
          outline
          :color="styleCategory"
          class="chip"
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
          :price="item.price"
          @click="open('bottom')"
        ></card-item>
      </div>
    </div>
  </q-page>
</template>

<script>
import CardItem from "../components/CardItem.vue";
import { ref } from "vue";

export default {
  components: {
    CardItem,
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
        },
        {
          title: "Bebidas",
        },
        {
          title: "Combo",
        },
        {
          title: "Doce",
        },
        {
          title: "Doce",
        },
        {
          title: "Doce",
        },
        {
          title: "Doce",
        },
      ],
      shape: ref(["line"]),
      open() {
        dialog.value = true;
      },
    };
  },
  computed: {
    styleCategory() {
      return "grey-8";
    },
  },
  methods() {},
};
</script>

<style lang="scss" scoped>
.dialog {
  height: 95vh;
  border-radius: 15px 15px 0px 0px !important;
  .body-iphone {
    width: 100%;
    .iphone {
      height: 7px;
      width: 100px;
      background-color: #d9d9d9;
      border-radius: 20px;
      margin: auto;
    }
  }
  .btn-buy {
    text-transform: none;
    font-size: 16px;
    width: 100%;
    height: 45px;
  }

  .img-card-section {
    width: 100%;
    height: 255px;
    background-color: black;
  }
  .text-card-section,
  .text-card-section-2 {
    color: #949494;
  }
  .text-card-section-2 {
    font-size: 13px;
  }
  .counter {
    display: flex;
    align-content: center;
    align-items: center;
    .btn-resize {
      width: 24px !important;
      height: 24px !important;
    }
    .counter-num {
      font-size: 16px;
      font-weight: bold;
      margin: 0 13px;
    }
  }
  .price {
    font-size: 18px;
    font-weight: bold;
  }
}
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
    margin-bottom: 68px;
  }
  .list-category {
    overflow-x: auto;
    overflow-y: hidden;
    height: auto;
    white-space: nowrap;
    padding: 0.5rem 1rem;
    .chip {
      cursor: pointer;
    }
  }
  ::-webkit-scrollbar {
    height: 3px;
  }
}
</style>
