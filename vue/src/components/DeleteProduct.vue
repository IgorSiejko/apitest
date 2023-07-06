<script>
import axios from 'axios';

export default {
  name: 'deleteData',
  data() {
    return {
      dataId: null,
      deletionMessage: ''
    };
  },
  methods: {
    deleteDataById() {
      axios.delete(`http://localhost:1337/api/products/${this.productId}`)
        .then(response => {
          this.deletionMessage = 'Data deleted successfully';
          this.dataId = null;
        })
        .catch(error => {
          this.deletionMessage = 'Operation failed';
          console.error(error);
        });
    }
  }
};
</script>
<template>
    <div>
    <h2>Data Deletion</h2>

    <form @submit.prevent="deleteDataById">
      <label for="dataId">Data ID:</label>
      <input type="number" id="productId" v-model="dataId" required>

      <button type="submit">Delete Data</button>
    </form>

    <div v-if="deletionMessage">{{ deletionMessage }}</div>
  </div>
</template>