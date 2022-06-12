<template>
  <section>
    <header>
      <h1>My Friends</h1>
    </header>
    <ul>
      <li>
        <friend-contact
          v-for="friend in friends"
          :key="friend.id"
          :id="friend.id"
          :name="friend.name"
          :phone-number="friend.phone"
          :email-address="friend.email"
          :is-favorite="friend.isFavorite"
          @toggle-favorite="toggleFavoriteStatus"
        >
        </friend-contact>
      </li>
    </ul>
  </section>
</template>

<script>
export default {
  data() {
    return {
      friends: [
        {
          id: "manuel",
          name: "Manuel Lorenz",
          phone: "0123 45678 90",
          email: "manuel@localhost.com",
          isFavorite: true,
        },
        {
          id: "julie",
          name: "Julie Jones",
          phone: "0987 654421 21",
          email: "julie@localhost.com",
          isFavorite: false,
        },
      ],
    };
  },
  methods: {
    toggleFavoriteStatus(friendId) {
      const favoriteFriend = this.friends.find(friend => friend.id === friendId);
      favoriteFriend.isFavorite = !favoriteFriend.isFavorite;
    }
  }
};
</script>
