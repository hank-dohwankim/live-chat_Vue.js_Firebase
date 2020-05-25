<template>
  <div class="welcome container">
    <div class="card">
      <div class="card-content center-align">
        <h2>Vue Live Chat</h2>
        <form @submit.prevent="enterChat">
          <label for="name">Please enter your name :</label>
          <input type="text" name="name" v-model="name" />
          <p v-if="feedback" class="red-text">{{ feedback }}</p>
          <button class="btn teal">Enter Chat Room</button>
        </form>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: "Welcome",
  data() {
    return {
      name: null,
      feedback: null
    };
  },
  methods: {
    enterChat() {
      if (this.name) {
        this.$router.push({ name: "Chat", params: { name: this.name } });
      } else {
        this.feedback = "Please enter your name";
      }
    }
  }
};
</script>

<style>
.welcome {
  max-width: 400px;
  margin-top: 10px;
}
.welcome h2 {
  font-size: 2.5em;
  color: #34495e;
}
.welcome button {
  margin: 30px auto;
}
</style>
