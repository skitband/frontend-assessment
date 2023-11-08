<script setup>

defineProps({
  msg: String,
})

</script>

<template>
  <header class="py-5 banner-image">
    <div class="banner-overlay"></div>
    <div class="banner-content">
      <h1 class="display-2 text-white fw-bolder">{{ msg }}</h1>
      <p class="h3 text-white mb-0 fw-light">Lorem ipsum dolor sit amet, consectetur adipiscing elit</p>
    </div>
  </header>
</template>
