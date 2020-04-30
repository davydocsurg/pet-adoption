<template>
  <div class="abt">
    <h4>Name: {{ animal.name }}</h4>
    <p>Age: {{ animal.age }}</p>
    <p>Breed: {{ animal.breed }}</p>
  </div>
</template>

<script>
import { mapState } from 'vuex'

export default {
  data () {
    return {
      animal: {}
    }
  },
  computed: {
    ...mapState([
      'dogs',
      'cats'
    ])
  },
  mounted () {
    const animal = this[this.$route.params.species][this.$route.params.id]
    this.animal = animal
  }
}
</script>

<style lang="css">
  .abt {
    text-align: left;
  }
</style>
