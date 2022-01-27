<template>
  <ul>
    <li v-for="(item, index) in products" :key="index" >
      <slot :item="item">
        {{ item.name }}
      </slot>
    </li>
  </ul>
</template>

<script>
export default {
  name: 'productsList',
  props: {
    products: {
      type: Array,
      required: true
    }
  }
}
</script>

<style scoped>
</style>
