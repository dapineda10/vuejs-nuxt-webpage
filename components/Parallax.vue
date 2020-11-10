<template>
  <v-parallax :height="parallaxConfiguration.height" :src="parallaxConfiguration.photo">
  <slot></slot>
  </v-parallax>
</template>

<script>
  export default {
     props: ['parallaxConfiguration']
    }
</script>