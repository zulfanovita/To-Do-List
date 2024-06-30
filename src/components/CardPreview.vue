<template>
    <div>
      <h2>Preview Your Greeting Card</h2>
      <div v-if="card">
        <p>Recipient: {{ card.recipient }}</p>
        <p>Message: {{ card.message }}</p>
      </div>
      <div v-else>
        <p>No card created yet</p>
      </div>
    </div>
  </template>
  
  <script>
  export default {
    props: {
      card: {
        type: Object,
        default: null
      }
    }
  };
  </script>
  
  <style scoped>
  /* Tambahkan gaya sesuai preferensi Anda */
  </style>
  