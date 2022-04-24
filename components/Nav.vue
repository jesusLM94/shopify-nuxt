<template>
  <header class="border-b sticky top-0 z-20 bg-white">
    <div
      class="flex items-center justify-between max-w-6xl pt-4 pb-2 px-4 mx-auto lg:max-w-screen-xl"
    >
      <NuxtLink to="/">
        <a class="cursor-pointer"
          ><span class="text-lg pt-1 font-bold">First Item</span></a
        >
      </NuxtLink>
      <a class="text-md font-bold cursor-pointer">Cart</a>
    </div>
  </header>
</template>

<script>
export default {
  name: 'AppNav',
}
</script>
