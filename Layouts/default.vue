<template>
  <div class='flex flex-col justify-between min-h-screen'>
    <AppNav />
    <Nuxt />
    <footer>
      Footer
    </footer>
  </div>

</template>

<script>
import AppNav from '../components/Nav.vue'

export default {
  name: 'AppLayout',
  components: { AppNav },
}
</script>
