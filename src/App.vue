<template>
  <ProductsList :products="products" />

  <br>

  <ProductsList :products="products">
    <template v-slot:default="slotProps">
        <img :src="slotProps.item.image" />
        {{ slotProps.item.name.toUpperCase() }}
    </template>
  </ProductsList>
</template>

<script>
import ProductsList from './components/productsList.vue'

export default {
  name: 'App',
  components: {
    ProductsList
  },
  setup() {
    const products = [
      {
        name: 'Magnifying Glass',
        image: 'magnifying.jpg'
      },
      {
        name: 'Light Bulb',
        image: 'bulb.jpg'
      }
    ];
 
    return { 
      products
    }
  }
}
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
