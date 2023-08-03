<template>
  <div class="chosen-items">
    <h1 class="chosen-items__title">Chosen user's items:</h1>
    <ul class="chosen-items__list">
      <li v-for="item in chosenUsersStuff" :key="item.id" class="chosen-item">
        <h2 class="chosen-item__name">{{ item.name }}</h2>
      </li>
    </ul>
  </div>
</template>

<script>
export default {
  props: ["chosenUsersStuff"],
};
</script>

<style scoped>
.chosen-items {
  padding: 15px;
  border: 5px solid blue;
  text-align: center;
  width: 50%;
}

.chosen-items__list {
  display: flex;
  justify-content: space-around;
  flex-wrap: wrap;
  list-style: none;
  padding: 0;
}

.chosen-item {
  width: 70px;
  min-height: 70px;
  padding: 5px;
  border: 5px solid lightblue;
  margin-right: 2px;
  margin-bottom: 6px;
}
</style>
