<template>
  <b-container fluid >
    <b-row  class="justify-content-md-center">
        <b-card :header="data.name" class="text-center mb-2 mr-4" v-for="(data, index) in restaurant" :key="index"
                border-variant="primary"
                header-bg-variant="primary"
                header-text-variant="white"
                align="center"
                style="max-width: 20rem;">
          <b-card-text>{{data.formatted_address}}</b-card-text>
        </b-card>
    </b-row>
  </b-container>
</template>

<script>
import serviceRestaurant from '@/services/restaurant'

export default {
  name: 'SCG',
  props: {
    msg: String
  },
  data: () => ({
    restaurant: null
  }),
  mounted () {
    serviceRestaurant().then(data => {
      this.restaurant = data
    })
  },
  methods: {}
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped lang="stylus">

</style>
