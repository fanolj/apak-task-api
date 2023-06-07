<template>
    <div>
      <h2>Data Display</h2>
      <ul>
        <li>Name-----Area</li>
        <li v-for="item in data" :key="item.id">
          {{ item.name.common }} - {{ item.area }} km2
        </li>
      </ul>
    </div>
  </template>
  
  <script>
  export default {
    props: {
      data: {
        type: Object,
        required: true
      }
    }
  };
  </script>