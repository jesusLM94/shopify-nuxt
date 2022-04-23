<template>
  <NuxtLink :to="navLink">
    <a class="group">
      <div class="w-full bg-gray-200 rounded-3xl overflow-hidden">
        <div class="relative group-hover:opacity-75 h-72">
          <img class='object-cover min-w-full min-h-full' :src="imgUrl" :alt="imgAltText"/>
        </div>
      </div>
      <h3 class="mt-4 text-lg font-medium text-gray-900">{{ title }}</h3>
      <p class="mt-1 text-sm text-gray-700">{{ price }}</p>
    </a>
  </NuxtLink>
</template>

<script>
export default {
  name: 'ProductList',
  props: {
    product: {
      node: {
        title: String,
        handle: String,
        priceRange: {
          minVariantPrice: {
            amount: Number
          }
        },
        images: {
          edges: [
            {
              node: {
                url: String,
                altText: String
              }
            }
          ]
        }
      },
    }
  },
  data() {
    const { handle, title, priceRange, images } = this.product.node
    const { url, altText } = images.edges[0].node
    const price = priceRange.minVariantPrice.amount

    return {
      handle,
      title,
      imgUrl: url,
      imgAltText: altText,
      price
    }
  },
  computed: {
    navLink() {
      return `products/${this.handle}`
    }
  }

}
</script>
