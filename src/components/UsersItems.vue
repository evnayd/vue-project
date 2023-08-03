<template>
  <div class="items">
    <h1 class="items__title">Users items:</h1>
    <ul class="items__list">
      <li
        @click="getItem(item)"
        class="item"
        v-for="item in usersStuff"
        :key="item.id"
      >
        <h2 class="item__name">{{ item.name }}</h2>
      </li>
    </ul>
  </div>
</template>

<script>
export default {
  props: ["usersStuff"],
  methods: {
    getItem(item) {
      this.$emit("getChosenItem", item);
    },
  },
};
</script>

<style scoped>
.items {
  min-width: 500px;
  padding: 15px;
  border: 5px solid green;
  text-align: center;
}

.items__title {
  margin-bottom: 10px;
}

.items__list {
  display: flex;
  justify-content: space-between;
  flex-wrap: wrap;
  list-style: none;
  padding: 0;
}

.item {
  width: 100px;
  height: 100px;
  padding: 5px;
  border: 5px solid greenyellow;
  margin-right: 2px;
  margin-bottom: 10px;
  cursor: pointer;
}
</style>
