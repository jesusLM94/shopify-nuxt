<template>
  <div>
    {{ product.title }}
  </div>
</template>

<script>
import { getAllProducts, getProduct } from '../../api'

export default {
  name: 'ProductsPage',
  data() {
    return {
      product: {},
    }
  },

  async fetch() {
    this.products = await getAllProducts()
    this.product = await getProduct(this.$route.params.slug)
  },

  generate: {
    routes() {
      return this.products.map((product) => {
        return `products/${product.node.handle}`
      })
    },
  },
}
</script>
