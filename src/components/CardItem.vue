<template>
  <q-card class="my-card">
    <q-img :src="img" class="img-card" />
    <q-card-section class="q-py-sm">
      <div class="row no-wrap items-center">
        <div class="col text-h6 ellipsis">{{ title }}</div>
      </div>
    </q-card-section>
    <q-card-section class="q-pt-none q-pb-sm">
      <div class="text-subtitle2 text-positive" style="font-size: 16px">
        R$ {{ price }}
      </div>
    </q-card-section>
  </q-card>
</template>

<script>
export default {
  props: {
    title: undefined,
    img: undefined,
    price: undefined,
  },
  data() {
    return {};
  },
};
</script>

<style lang="scss" scoped>
.my-card {
  width: 49%;
  max-width: 230px;
  height: 280px;
}

.img-card {
  width: 100%;
  height: 100%;
  max-height: 200px;
}
</style>
