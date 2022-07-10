<template>
  <q-header class="bg-white"> </q-header>
  <q-page class="body">
    <q-card-section class="logo">
      <div class="h1">CAPITAL</div>
      <div class="h2">Delivery</div>
    </q-card-section>
    <q-card-section class="form">
      <div class="q-gutter-y-md column">
        <q-input standout="bg-black text-white" v-model="text" label="Email" />
        <q-input
          standout="bg-black text-white"
          v-model="text"
          label="Password"
        />
        <q-btn class="btn-login" label="Login" to="/" />
        <router-link class="link-register" to="/register">Register</router-link>
      </div>
    </q-card-section>
  </q-page>
</template>

<script>
import { defineComponent } from "vue";

export default defineComponent({
  name: "login-page",
});
</script>

<style lang="scss" scoped>
.body {
  background-color: rgb(255, 255, 255);
  height: 100vh;
}
.btn-login {
  height: 50px;
}
.link-register {
  text-decoration: none;
  color: rgb(112, 112, 112);
  font-weight: 600;
  font-size: 16px;
  margin: auto;
  padding: 1rem;
}

.logo {
  height: 40%;
  align-items: center;
  text-align: center;
  .h1 {
    padding-top: 4rem;
    font-size: 48px;
    font-weight: 700;
    font-family: "Segoe UI", Tahoma, Geneva, Verdana, sans-serif;
  }
  .h2 {
    font-size: 24px;
    font-weight: 600;
    font-family: "Segoe UI", Tahoma, Geneva, Verdana, sans-serif;
  }
}
.form {
  height: 60%;
}
</style>
