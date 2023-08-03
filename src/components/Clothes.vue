<template>
  <div class="box">
    <h1 class="box__title">Clothes:</h1>
    <ul class="box__list">
      <li
        @click="getClothesItem(item)"
        v-for="item in clothes"
        :key="item.id"
        class="item"
      >
        <h2 class="piece__name">{{ item.name }}</h2>
      </li>
    </ul>
  </div>
</template>

<script>
export default {
  props: ["clothes"],
  methods: {
    getClothesItem(item) {
      this.$emit("getClothesItem", item);
    },
  },
};
</script>
