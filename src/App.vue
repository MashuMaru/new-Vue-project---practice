<template>
  <section>
    <header>
      <h1>Friends Contacts</h1>
    </header>
    <new-friend v-on:add-contact="addContact"></new-friend>
    <ul>
      <friend-contact
        v-for="friend in friends"
        v-bind:key="friend.id"
        v-bind:id="friend.id"
        v-bind:name="friend.name"
        v-bind:phone-number="friend.phone"
        v-bind:email-address="friend.email"
        v-bind:is-favorite="friend.isFavorite"
        v-on:toggle-favorite="toggleFavoriteStatus"
      >
      </friend-contact>
    </ul>
  </section>
</template>

<script>

export default {

  data: function() {
    return {
      friends: [
        {
          id: "manuel",
          name: "Manuel Surname",
          phone: "123456",
          email: "manuel@local.com",
          isFavorite: true,
        },
        {
          id: "julie",
          name: "Julie Surname",
          phone: "987654",
          email: "julie@local.com",
          isFavorite: false,
        },
      ],
    };
  },
  methods: {
    toggleFavoriteStatus(friendId) {
      const identifiedFriend = this.friends.find(
        (friend) => friend.id === friendId
      );
      identifiedFriend.isFavorite = !identifiedFriend.isFavorite;
    },
    addContact(name, phone, email) {
      const newFriend  = {
        id: new Date().toISOString(),
        name: name,
        phone: phone, 
        email: email, 
        isFavorite: false
      }
      this.friends.push(newFriend);
    }

  },
};
</script>

<style>
@import url("https://fonts.googleapis.com/css2?family=Jost&display=swap");
@import "../public/styles.css";
</style>
