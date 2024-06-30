<template>
    <div>
      <h2>Create Your Greeting Card</h2>
      <form @submit.prevent="createCard">
        <label for="recipient">Recipient:</label>
        <input type="text" id="recipient" v-model="recipient" required />
        <label for="message">Message:</label>
        <textarea id="message" v-model="message" required></textarea>
        <button type="submit">Create Card</button>
      </form>
    </div>
  </template>
  
  <script>
  export default {
    data() {
      return {
        recipient: '',
        message: ''
      };
    },
    methods: {
      createCard() {
        this.$emit('card-created', {
          recipient: this.recipient,
          message: this.message
        });
        this.recipient = '';
        this.message = '';
      }
    }
  };
  </script>
  
  <style>
  /* CardMaker.vue */

form {
  display: flex;
  flex-direction: column;
  max-width: 300px;
  margin: 0 auto;
}

input,
textarea {
  margin-bottom: 10px;
  padding: 10px;
  border: 1px solid #ccc;
  border-radius: 5px;
}

button {
  background-color: #007bff;
  color: #fff;
  border: none;
  padding: 10px;
  cursor: pointer;
  border-radius: 5px;
}

button:hover {
  background-color: #0056b3;
}

/* CardPreview.vue */

.card-preview {
  border: 1px solid #ccc;
  padding: 20px;
  border-radius: 5px;
  background-color: #f9f9f9;
  max-width: 300px;
  margin: 0 auto;
}

.card-preview p {
  margin-bottom: 10px;
}

/* App.vue */

#app {
  display: flex;
  justify-content: space-around;
  padding: 20px;
}

  </style>
  