<template>
    <div>
      <h1>{{ message }}</h1>
    </div>
  </template>
  
  <script>
  import axios from 'axios';
  
  export default {
    data() {
      return {
        message: '',
      };
    },
    mounted() {
      axios.get('/api/message') // Relative path to the backend API
        .then((response) => {
          this.message = response.data.message;
        })
        .catch((error) => {
          console.error('Error:', error);
        });
    },
  };
  </script>
  