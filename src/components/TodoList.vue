<template>
    <div>
      <h1>Todo List</h1>
      <input v-model="newItem" @keyup.enter="addItem" placeholder="Add new item" />
      <ul>
        <li v-for="(item, index) in items" :key="index">
          {{ item }} <button @click="removeItem(index)">Delete</button>
        </li>
      </ul>
    </div>
  </template>
  
  <script>
  export default {
    data() {
      return {
        newItem: '',
        items: []
      };
    },
    methods: {
      addItem() {
        if (this.newItem.trim() !== '') {
          this.items.push(this.newItem.trim());
          this.newItem = '';
        }
      },
      removeItem(index) {
        this.items.splice(index, 1);
      }
    }
  };
  </script>
  
  <style scoped>
  ul {
    list-style-type: none;
  }
  </style>
  