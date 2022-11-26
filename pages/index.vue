<template>
  <div>
    <div class="container">
      <div class="row">
        <div v-for="home in homes" :key="home.objectID" class="col-md-4">
          <HomeCard :home="home" />
        </div>
      </div>
    </div>
  </div>
</template>

<script>
import homes from '~/data/homes'
export default {
  name: 'IndexPage',
  head(){
    return {
      title: 'Home',
      meta: [{
        name: 'Description',
        content: 'This is a homepage!',
        hid: 'Description'
      }],
    }
  },
  data() {
    return {
      homes: homes.slice(0, 3)
    }
  },
}
</script>
