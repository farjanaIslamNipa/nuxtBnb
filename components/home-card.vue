<template>
    <nuxt-link :to="`/home/${home.objectID}`" class="d-block">
      <img class="img-fluid" :src="home.images[0]" alt="">
      <h3>{{ home.title }}</h3>
      <p><span>{{ home.location.address}}</span>, <span>{{ home.location.city }}</span>, {{ home.location.state}}</p>
      <p>{{ home.guests }} guests</p>
      <h2>{{ home.pricePerNight }} / Night</h2>
    </nuxt-link>
</template>

<script>
  export default {
    name: 'HomeCard',
    props: {
      home: {
        type: Object,
        required: true
      }
    },
    data() {
    return {
      
    }
  },
  }
</script>

<style scoped>

</style>