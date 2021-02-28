<template>
  <li>
    <h2>{{ friend.name }}</h2>
    <button v-on:click="toggleDetails">{{detailsAreVisible ? 'Hide details' : 'Show details'}}</button>
    <ul v-show="detailsAreVisible">
      <li><strong>Phone:</strong>{{ friend.phone }}</li>
      <li><strong>Email:</strong>{{ friend.email }}</li>
    </ul>
  </li>
</template>

<script>
export default {
  data() {
    return {
      detailsAreVisible: false,
      friend: 
        {
          id: "manuel",
          name: "Manuel Surname",
          phone: "0123 45678 90",
          email: "manuel@email.com",
        },
    };
  },
  methods: {
    toggleDetails() {
      this.detailsAreVisible = !this.detailsAreVisible;
    },
  },
};
</script>

<style></style>
