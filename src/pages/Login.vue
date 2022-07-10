<template>
  <q-header class="bg-white"> </q-header>
  <q-page class="body">
    <q-card-section class="logo">
      <div class="h1">CAPITAL</div>
      <div class="h2">Delivery</div>
    </q-card-section>
    <q-card-section class="form">
      <div class="q-gutter-y-md column">
        <q-input
          outlined
          v-model="email"
          label="Email"
          type="email"
          :rules="[(val) => !!val || 'Email is required']"
          lazy-rules
        />
        <q-input
          outlined
          v-model="password"
          label="Password"
          type="password"
          :rules="[(val) => !!val || 'Password is required']"
          lazy-rules
        />
        <q-btn
          class="btn-login bg-grey-8 text-white"
          label="Login"
          @click="login"
        />
        <router-link class="link-register" to="/register">Register</router-link>
      </div>
    </q-card-section>
  </q-page>
</template>

<script>
import { defineComponent } from "vue";
import { ref } from "vue";

export default defineComponent({
  name: "login-page",
  setup() {
    return {
      email: ref(""),
      password: ref(""),
    };
  },
  methods: {
    login() {
      if (this.email !== "luiz" && this.password !== "1234") {
        this.$router.push("/");
      } else {
        console.log("error!");
      }
    },
  },
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
  color: rgb(122, 122, 122);
  font-weight: 500;
  font-size: 16px;
  margin: auto;
  padding: 1rem;
}

.logo {
  height: 40%;
  align-items: center;
  text-align: center;
  .h1 {
    padding-top: 10rem;
    font-size: 48px;
    font-weight: 700;
    color: rgb(36, 36, 36);
    font-family: "Segoe UI", Tahoma, Geneva, Verdana, sans-serif;
  }
  .h2 {
    font-size: 24px;
    font-weight: 600;
    color: rgb(85, 85, 85);
    font-family: "Segoe UI", Tahoma, Geneva, Verdana, sans-serif;
  }
}
.form {
  height: 60%;
  max-width: 600px;
  margin: auto;
}
</style>
