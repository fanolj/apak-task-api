<template>
  <div>
    <h1>Data Display App</h1>
    <DataDisplay :data="data" v-if="dataLoaded" />
    <div v-else>Loading data...</div>
    <div v-if="error">{{ error }}</div>
  </div>
</template>

<script>
import axios from 'axios';
import DataDisplay from './components/DataDisplay.vue';

export default {
  components: {
    DataDisplay
  },
  data() {
    return {
      data: null,
      dataLoaded: false,
      error: null
    };
  },
  mounted() {
    this.fetchData();
  },
  methods: {
    fetchData() {
      axios.get('https://demo.erpnext.com/api/resource/User')
        .then(response => {
          this.data = response.data;
          this.dataLoaded = true;
        })
        .catch(error => {
          this.error = 'Error fetching data: ' + error.message;
        });
    }
  }
};
</script>


<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
