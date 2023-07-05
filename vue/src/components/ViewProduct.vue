<script>
import axios from 'axios'
export default 
{
    name: 'products',
    data()
    {
        return{
            products: []
        }
    },
    mounted()
    {
        this.getProducts();
    },
    methods:
    {
        getProducts() {
        axios.get('http://localhost:1337/api/products').then(response => {
        this.products = response.data.data.map(item => item.attributes);
        console.log(this.products);
        }).catch(error => {
        console.error(error);
        });
        }
    },
}
</script>
<template>
    <table>
        <thead>
            <tr>
                <td>Name</td>
                <td>Description</td>
                <td>Price</td>
                <td>Category</td>
            </tr>
        </thead>    
        <tbody>
            <tr v-for="(products, index) in this.products" :key="index">
                <td>{{ products.name }}</td>
                <td>{{ products.description }}</td>
                <td>{{ products.price }}</td>
                <!-- need to create api request that will bring the category from relation-->
                <td>placeholder</td>
           </tr>
        </tbody>
    </table>
</template>
<style scoped>

    thead
    {
        background-color: hsla(160, 100%, 37%, 1);
        color: black;
    }
    td
    {
        font-weight: 500;
        padding: 10px;
        box-sizing: border-box;
    }
    tbody
    {
        background-color: white;
        color: black;
    }

</style>