<script>
    import axios from 'axios';

    export default {
    name: 'addProduct',
    data() {
        return {
            Name: '',
            Description: '',
            Price: 0
        };
    },
    methods: {
        addProduct() {
        const newProduct = 
        {
            name: this.Name,
            description: this.Description,
            price: this.Price
        };

        axios.post('http://localhost:1337/api/products', { data: newProduct })
            .then(response => {
            console.log('Product added successfully:', response.data);
            })
            .catch(error => {
            console.error('Error adding product:', error);
            });
        }
    }
    };


</script>
<template>
    <section>
        <header><h1>Add Data</h1></header>
        <div>
        <form @submit.prevent="addProduct">
            <label for="productName">Product Name:</label>
            <input type="text" id="productName"  class="addProductInput" v-model="productName" required>
            <br>
    
            <label for="productDescription">Product Description:</label>
            <textarea id="productDescription" class="addProductInput" v-model="productDescription" required></textarea>
            <br>
    
            <label for="productPrice">Product Price:</label>
            <input type="number" id="productPrice" class="addProductInput" v-model="productPrice" required>
            <br>
    
            <button type="submit">Add Product</button>
        </form>
        </div>
    </section>
  </template>
<style scoped>
button
{
    background-color: hsla(160, 100%, 37%, 1);
    border: none;
    font-weight: 600;
    width: 100px;
    height: 50px;
}

label
{
    display:inline-block;
    width: 150px;
}
.addProductInput
{
    width: 200px;
    background-color: var(--vt-c-text-dark-2);
    border: none;
}
</style>