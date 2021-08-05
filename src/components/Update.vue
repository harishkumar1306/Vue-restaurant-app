<template>
  <Header />
  <h1>Hello {{ name }}, Welcome to Update Restaurat page!!</h1>
  <form class="add">
    <input
      type="text"
      name="name"
      placeholder="Enter name"
      v-model="restaurant.name"
    />
    <input
      type="text"
      name="address"
      placeholder="Enter address"
      v-model="restaurant.address"
    />
    <input
      type="text"
      name="contact"
      placeholder="Enter contact"
      v-model="restaurant.contact"
    />
    <button v-on:click="updateRestaurant" type="button">
      Update Restaurant
    </button>
  </form>
</template>

<script>
import Header from "./Header.vue";
import axios from "axios";

export default {
  name: "Update",
  data() {
    return {
      name: "",
      restaurant: {
        name: "",
        address: "",
        contact: "",
      },
    };
  },
  components: {
    Header,
  },
  methods: {
    async updateRestaurant() {
      const result = await axios.put(
        "http://localhost:3000/restaurants/" + this.$route.params.id,
        {
          name: this.restaurant.name,
          address: this.restaurant.address,
          contact: this.restaurant.contact,
        }
      );
      if (result.status == 200) {
        this.$router.push({ name: "Home" });
      }
    },
  },
  async mounted() {
    let user = localStorage.getItem("user-info");
    this.name = JSON.parse(user).name;
    if (!user) {
      this.$router.push({ name: "SignUp" });
    }
    const result = await axios.get(
      "http://localhost:3000/restaurants/" + this.$route.params.id
    );
    this.restaurant = result.data;
  },
};
</script>
