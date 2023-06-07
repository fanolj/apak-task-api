<template>
    <div>
      <h2>Data Display</h2>
      <ul>
        <li v-for="item in data" :key="item.id">
          {{ item.name }} - {{ item.value }}
        </li>
      </ul>
    </div>
  </template>
  
  <script>
  export default {
    props: {
      data: {
        type: Array,
        required: true
      }
    }
  };
  </script>