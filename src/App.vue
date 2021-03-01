<template>
  <section>
    <header>
      <h1>Friends Contacts</h1>
    </header>
    <ul>
      <friend-contact
        name="Manuel Surname"
        phone-number="123456"
        email-address="manuel@local.com"
        is-favorite="1"
      >
      </friend-contact>
      <friend-contact
        name="Julie Surname"
        phone-number="987654"
        email-address="julie@local.com"
        is-favorite="0"
      >
      </friend-contact>
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
          phone: "123456",
          email: "manuel@local.com",
        },
        {
          id: "julie",
          name: "Julie Surname",
          phone: "987654",
          email: "julie@local.com",
        },
      ],
    };
  },
};
</script>

<style>
@import url("https://fonts.googleapis.com/css2?family=Jost&display=swap");
@import "../public/styles.css";
</style>
