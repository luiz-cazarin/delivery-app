<template>
  <q-header class="bg-white">
    <q-toolbar class="q-pt-xl q-pb-sm">
      <q-btn color="red" flat round dense icon="chevron_left" to="/" />
      <q-space />
      <q-title class="text-black text-bold">{{ "Orders" }}</q-title>
      <q-space style="margin-right: 34px" />
    </q-toolbar>
  </q-header>
  <q-page>
    <div class="body">
      <div class="header-text">
        <p class="t1">Thak you!</p>
        <p class="t2">You Order</p>
      </div>
      <div class="body-list">
        <q-list>
          <q-item clickable v-ripple>
            <q-item-section avatar>
              <q-avatar rounded class="avatar">
                <img
                  src="https://s.calendarr.com/upload/datas/pi/zz/pizza_c.jpg?auto_optimize=low&width=640"
                />
              </q-avatar>
            </q-item-section>
            <q-item-section class="desc-item">
              <div class="title">Pizza grande</div>
              <div class="description">1/2 calabresa<br />1/2 queijo</div>
              <div class="content-item">
                <div class="body-price">
                  R$
                  <div class="price">38,00</div>
                </div>
                <div class="counter">
                  <q-btn round color="grey-4" class="btn-resize" dense>-</q-btn>
                  <div class="counter-num">{{ "1" }}</div>
                  <q-btn round color="primary" class="btn-resize" dense
                    >+</q-btn
                  >
                </div>
              </div>
            </q-item-section>
          </q-item>
        </q-list>
      </div>
      <div class="body-footer-next">
        <q-item-section>
          <div class="section-footer">
            <div>Total com a entrega</div>
            <div>R$ 58,00</div>
          </div>
        </q-item-section>
        <q-btn class="btn-footer">Continuar</q-btn>
      </div>
    </div>
  </q-page>
</template>

<script>
import { defineComponent } from "vue";

export default defineComponent({
  name: "orders-page",
});
</script>

<style lang="scss" scoped>
.body {
  height: 80vh;
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
  .body-list {
    .avatar {
      font-size: 75px !important;
    }
    .desc-item {
      .title {
        font-size: 16px;
        font-weight: 600;
      }
      .description {
        font-size: 14px;
        font-weight: 400;
        color: rgb(100, 100, 100);
      }
      .content-item {
        padding-top: 0.3rem;
        justify-content: space-between;
        display: flex;
      }
      .body-price {
        display: flex;
        font-size: 18px;
        font-weight: 600;
        .price {
          margin-left: 0.5rem;
        }
      }
      .counter {
        display: flex;
        align-content: center;
        align-items: center;
        .btn-resize {
          width: 16px !important;
          height: 16px !important;
        }
        .counter-num {
          font-size: 16px;
          font-weight: bold;
          margin: 0 13px;
        }
      }
    }
  }
  .body-footer-next {
    position: fixed;
    bottom: 0;
    padding: 1.5rem;
    width: 100%;
    height: 260px;
    border-radius: 10px;
    box-shadow: 0px -4px 4px rgba(0, 0, 0, 0.1);
    .section-footer {
      display: flex;
      justify-content: space-between;
      font-size: 16px;
      font-weight: 700;
    }
    .btn-footer {
      margin-top: 2rem;
      width: 100%;
      height: 60px;
      font-family: "Segoe UI", Tahoma, Geneva, Verdana, sans-serif;
      font-weight: 600;
      font-size: 16px;
      background: red;
      color: white;
      border-radius: 10px;
    }
  }
}
</style>
>
