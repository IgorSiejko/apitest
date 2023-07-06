<script setup>
import HelloWorld from './components/HelloWorld.vue'
import AddProduct from './components/AddProduct.vue'
import ViewProduct from './components/ViewProduct.vue'
import DeleteProduct from './components/DeleteProduct.vue';
</script>

<template>
  <header>
    <img alt="Vue logo" class="logo" src="./assets/logo.svg" width="125" height="125" />

    <div class="wrapper">
      <HelloWorld msg="You did it!" />
    </div>
  </header>

  <main>
    <ViewProduct/>
    <AddProduct/>
    <DeleteProduct/>
  </main>
</template>

<style scoped>


.logo {
  display: block;
  margin: 0 auto 2rem;
}

@media (min-width: 1024px) {
  header {
    display: flex;
    place-items: center;
    padding-right: calc(var(--section-gap) / 2);
  }


}
</style>
