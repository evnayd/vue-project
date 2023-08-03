<template>
  <div id="app">
    <main>
      <div class="upper-block">
        <chosen-users-items :chosenUsersStuff="chosenUsersStuff">
        </chosen-users-items>
        <chosen-clothes :chosenClothes="chosenClothes"></chosen-clothes>
      </div>
      <div class="lower-block">
        <users-items
          @getChosenItem="handleChosenUserItem"
          :usersStuff="usersStuff"
        ></users-items>
        <clothes
          @getClothesItem="handleGetClothesItem"
          :clothes="clothes"
        ></clothes>
      </div>
    </main>
  </div>
</template>

<script>
import Clothes from "./components/Clothes.vue";
import UsersItems from "./components/UsersItems.vue";
import ChosenUsersItems from "./components/ChosenUsersItems.vue";
import ChosenClothes from "./components/ChosenClothes.vue";

export default {
  components: {
    Clothes,
    UsersItems,
    ChosenUsersItems,
    ChosenClothes,
  },

  data() {
    return {
      chosenUsersStuff: [],
      chosenClothes: {
        name: "",
        id: "",
      },
      usersStuff: [
        {
          id: 1,
          name: "Shoes 1",
        },
        {
          id: 2,
          name: "Shoes 2",
        },
        {
          id: 3,
          name: "Shoes 3",
        },
        {
          id: 4,
          name: "Shoes 4",
        },
        {
          id: 5,
          name: "T-shirt 1",
        },
        {
          id: 6,
          name: "T-shirt 2",
        },
        {
          id: 7,
          name: "T-shirt 3",
        },
        {
          id: 8,
          name: "T-shirt 4",
        },
      ],
      clothes: [
        {
          id: 11,
          name: "Jacket 1",
        },
        {
          id: 12,
          name: "Jacket 2",
        },
        {
          id: 13,
          name: "Jacket 3",
        },
        {
          id: 14,
          name: "Jacket 4",
        },
        {
          id: 15,
          name: "Hoodie 1",
        },
        {
          id: 16,
          name: "Hoodie 2",
        },
        {
          id: 17,
          name: "Hoodie 3",
        },
        {
          id: 18,
          name: "Hoodie 4",
        },
      ],
    };
  },

  computed: {
    canAddItem() {
      return this.chosenUsersStuff.length < 7;
    },
    canAddClothes() {
      return !this.chosenClothes.name;
    },
  },
  methods: {
    handleChosenUserItem(item) {
      console.log("item user", item);
      let newarr = JSON.parse(JSON.stringify(this.chosenUsersStuff));
      if (!newarr.some((itm) => itm.id === item.id) && this.canAddItem) {
        newarr.push(item);
      }
      this.chosenUsersStuff = newarr;
    },
    handleGetClothesItem(item) {
      if (this.canAddClothes) {
        const { name, id } = item;
        this.chosenClothes = { name, id };
      }
    },
  },
};
</script>

<style scoped>
.upper-block {
  display: flex;
  justify-content: space-between;
  margin-bottom: 50px;
  padding: 20px;
}

.lower-block {
  padding: 20px;
  display: flex;
  justify-content: space-between;
}
</style>
