<template>
  <li>
    <h2>{{ name }} {{ friendIsFavorite === "1" ? "(Favorite)" : null }}</h2>
    <button v-on:click="toggleFavorite">
      Toggle Favorite
    </button>
    <button v-on:click="toggleDetails">
      {{ detailsAreVisible ? "Hide details" : "Show details" }}
    </button>
    <ul v-show="detailsAreVisible">
      <li><strong>Phone:</strong>{{ phoneNumber }}</li>
      <li><strong>Email:</strong>{{ emailAddress }}</li>
    </ul>
  </li>
</template>

<script>
export default {
  // props: ["name", "phoneNumber", "emailAddress", "isFavorite"],
  props: {
    name: {
      type: String,
      required: true,
    },
    phoneNumber: {
      type: String,
      required: true,
    },
    emailAddress: {
      type: String,
      required: true,
    },
    isFavorite: {
      type: String,
      required: false,
      default: "0",
      validator: function(value) {
        return value === "1" || value === "0";
      },
    },
  },
  data: function() {
    return {
      detailsAreVisible: false,
      friend: {
        id: "manuel",
        name: "Manuel Surname",
        phone: "0123 45678 90",
        email: "manuel@email.com",
      },
      friendIsFavorite: this.isFavorite,
    };
  },
  methods: {
    toggleDetails() {
      this.detailsAreVisible = !this.detailsAreVisible;
    },
    toggleFavorite() {
      if (this.friendIsFavorite === "1") {
        this.friendIsFavorite = "0";
      } else {
        this.friendIsFavorite = "1";
      }
    },
  },
};
</script>

<style></style>
