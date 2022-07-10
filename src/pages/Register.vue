<template>
  <q-header class="bg-white">
    <q-toolbar class="q-pt-xl q-pb-sm">
      <q-btn color="red" flat round dense icon="chevron_left" to="/login" />
      <q-space />
      <q-title class="text-black text-bold">{{ "Register" }}</q-title>
      <q-space />
      <q-btn color="red" flat round dense to="/login" />
    </q-toolbar>
  </q-header>
  <q-page class="body">
    <q-card-section>
      <div class="header-text">
        <div class="t1">SignUp</div>
        <div class="t2">Informe os seus dados</div>
      </div>
    </q-card-section>
    <q-card-section class="form">
      <div class="q-gutter-y-md column">
        <q-input outlined v-model="text" label="Name" required />
        <q-input outlined v-model="text" label="Email" />
        <q-input outlined v-model="text" label="Password" />
        <q-input outlined v-model="text" label="Phone number" />
        <q-input outlined v-model="text" label="CPF" />
        <q-input outlined v-model="text" label="Address" />
        <div class="full-width row no-wrap justify-between">
          <q-input outlined v-model="text" label="CEP" style="width: 75%" />
          <q-input outlined v-model="text" label="N" style="width: 20%" />
        </div>
        <q-input outlined v-model="text" label="Reference" />
        <div>
          <q-checkbox v-model="right" label="Accept all terms & services" />
        </div>
        <q-btn
          class="btn-register bg-primary text-white"
          label="Register"
          to="/"
        />
      </div>
    </q-card-section>
  </q-page>
</template>

<script>
import { defineComponent } from "vue";

export default defineComponent({
  name: "register-page",
});
</script>

<style lang="scss" scoped>
.body {
  background-color: rgb(255, 255, 255);
  height: 100vh;
}
.btn-register {
  height: 50px;
  margin-bottom: 2rem;
}

.header-text {
  padding: 0;
  margin: 0;
  .t1 {
    font-family: "Segoe UI", Tahoma, Geneva, Verdana, sans-serif;
    font-weight: bold;
    font-size: 20px;
  }
  .t2 {
    font-family: "Segoe UI", Tahoma, Geneva, Verdana, sans-serif;
    font-weight: 600;
    font-size: 14px;
    color: rgba(0, 0, 0, 0.4);
  }
}

.form {
  height: 60%;
}
</style>
