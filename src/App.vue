<template>
  <section>
    <header>
      <h1>Friends Contacts</h1>
    </header>
    <ul>
      <friend-contact></friend-contact>
      <friend-contact></friend-contact>
    </ul>
  </section>
</template>

<script>
// import FriendContact from "./components/FriendContact.vue";
export default {
  // components: { FriendContact },
  data: function() {
    return {
      friends: [
        {
          id: "manuel",
          name: "Manuel Surname",
          phone: "0123 443 2342",
          email: "manuel@local.com",
        },
        {
          id: "julie",
          name: "Julie Surname",
          phone: "0123 443 2342",
          email: "julie@local.com",
        },
      ],
    };
  },
};
</script>

<style>
@import url('https://fonts.googleapis.com/css2?family=Jost&display=swap');
@import "../public/styles.css";
</style>
