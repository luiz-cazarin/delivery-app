<template>
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
        Se liga que essa deliciosa novidade vem para saciar a sua fome, vem
        comigo de pizza grande com borda recheada
      </div>
    </q-card-section>
    <q-card-section>
      <div
        class="fufull-width row no-wrap justify-between items-center content-center"
      >
        <div class="counter">
          <q-btn
            round
            color="grey-4"
            class="btn-resize"
            dense
            @click="decAmount"
            >-</q-btn
          >
          <div class="counter-num">{{ amount }}</div>
          <q-btn
            round
            color="primary"
            class="btn-resize"
            dense
            @click="addAmount"
            >+</q-btn
          >
        </div>
        <div class="price text-positive">R$ 38,00</div>
      </div>
    </q-card-section>
    <q-card-section class="bg-grey-3">
      <div class="text-subtitle2 text-grey-8">Deseja Adicionar algum item?</div>
      <div class="text-card-section-2">Escolha pelomenos uma opção.</div>
    </q-card-section>
    <q-card-section
      v-for="i in itemsExtra"
      :key="i.id"
      class="fufull-width row no-wrap justify-between"
    >
      <div>
        <div class="text-subtitle2 text-grey-8">{{ i.title }}</div>
        <div class="text-subtitle2 text-grey-8">
          + R$ {{ i.price.toFixed(2) }}
        </div>
      </div>
      <div class="text-card-section-2">
        <q-checkbox size="md" v-model="i.shape" val="md" @click="addExtra(i)" />
      </div>
    </q-card-section>
    <q-card-section class="full-width row justify-center">
      <q-btn class="btn-buy" color="primary" @click="addOrder()"
        >Adicionar ao carrinho</q-btn
      >
    </q-card-section>
  </q-card>
</template>

<script>
export default {
  data() {
    return {
      itemsExtra: [
        {
          id: 0,
          title: "Calabreza",
          price: 6.0,
          shape: false,
        },
        {
          id: 1,
          title: "Batata frita",
          price: 11.0,
          shape: false,
        },
      ],
      amount: 0,
    };
  },
  methods: {
    decAmount() {
      if (this.amount !== 0) {
        this.amount--;
      }
    },
    addAmount() {
      // check quantity in database
      this.amount++;
    },
    addExtra(el) {
      console.log(el);
    },
    addOrder() {},
  },
};
</script>

<style lang="scss" scoped>
::-webkit-scrollbar {
  width: 3px;
}
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
</style>
