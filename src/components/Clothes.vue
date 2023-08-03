<template>
  <div class="clothes">
    <h1 class="clothes__title">Clothes:</h1>
    <ul class="clothes__list">
      <li
        @click="getClothesItem(item)"
        v-for="item in clothes"
        :key="item.id"
        class="piece"
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
      console.log("item in component", item);
    },
  },
};
</script>

<style scoped>
.clothes {
  width: 50%;
  padding: 15px;
  border: 5px solid blue;
  text-align: center;
}

.clothes__title {
  margin-bottom: 10px;
}

.clothes__list {
  display: flex;
  justify-content: space-between;
  flex-wrap: wrap;
  list-style: none;
  padding: 0;
}

.piece {
  width: 100px;
  height: 100px;
  padding: 5px;
  border: 5px solid lightblue;
  margin-right: 2px;
  margin-bottom: 10px;
  cursor: pointer;
}
</style>
