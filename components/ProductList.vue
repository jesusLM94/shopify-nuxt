<template>
  <div class="bg-white">
    <div class="max-w-2xl mx-auto py-16 px-4 sm:py-24 sm:px-6 lg:max-w-7xl lg:px-8">
      <h2 class="text-2xl font-extrabold text-gray-900 mb-6">Products</h2>
      <div class="grid grid-cols-1 gap-y-10 gap-x-6 sm:grid-cols-2 lg:grid-cols-3 xl:grid-cols-4 xl:gap-x-8">
        <ProductCard v-for='product in products' :key='product.id' :product="product" />
      </div>
    </div>
  </div>
</template>

<script>
import { getProductsInCollection } from '../api'

export default {
  name: 'ProductList',
  data() {
    return {
      products: [],
    }
  },

  async mounted() {
    this.products = await getProductsInCollection()
  },

}
</script>
