<script>

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
        axios.get('http://localhost:1337/api/products').then(response => 
        {
            this.products = response.data.data.map(item => item.attributes);
            console.log(this.products);

        }).catch(error => {console.error(error);});
        }
    },
}
</script>
<template>

    

</template>