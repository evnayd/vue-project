<template>
  <div class="chosen-item">
    <h1 class="chosen-item__title">Chosen clothes:</h1>
    <div v-if="chosenClothes.name" class="item">
      <h2 class="item__name">{{ chosenClothes.name }}</h2>
    </div>
  </div>
</template>

<script>
export default {
  props: ["chosenClothes"],
};
</script>

<style scoped>
.chosen-item {
  border: 5px solid red;
  text-align: center;
  width: 50%;
  padding: 15px;
}

.item {
  width: 150px;
  height: 150px;
  border: 5px solid black;
  margin: 0 auto;
}
</style>
