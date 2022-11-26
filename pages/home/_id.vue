<template>
  <div>
    <div class="container">
      <div class="row">
        <div v-for="image in home.images" :key="image" class="col-md-4 mb-4">
          <img :src="image" class="img-fluid card-img" alt="">
        </div>
      </div>
      <h4>{{ home.title }}</h4>
      <h2>{{ home.pricePerNight }} / Night</h2>
      <div class="d-flex align-items-start">
        <img class="icon-img" src="/images/marker.svg" alt="">
        <p class="ms-2"><span>{{ home.location.address}}</span>, <span>{{ home.location.city }}</span>, <span>{{ home.location.state}}</span></p>
      </div>
      <div class="d-flex align-items-start">
        <img class="icon-img" src="/images/star.svg" alt="">
        <p class="ms-2">{{ home.guests }} guests, {{ home.bedrooms }} rooms, {{ home.beds }} beds, {{ home.bathrooms }} bath</p>
      </div>
    </div>
  </div>
</template>

<script>
  import homes from '~/data/homes'
  export default {
    name: 'SingleHome',
    data() {
      return {
        home: {}
      }
    },
    created () {
      const home = homes.find((home) => home.objectID == this.$route.params.id)
      this.home = home;
    },
  }
</script>

<style scoped>
.card-img{
  height: 300px;
  width: 440px;
  object-fit: cover;
}
.icon-img{
  height: 20px;
}
</style>