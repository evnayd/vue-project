<template>
  <div class="box">
    <h1 class="box__title">Chosen user's items:</h1>
    <ul class="box__list">
      <li v-for="item in chosenUsersStuff" :key="item.id" class="item">
        <h2>{{ item.name }}</h2>
      </li>
    </ul>
  </div>
</template>

<script>
export default {
  props: ["chosenUsersStuff"],
};
</script>
