<template>
  <div>
    <h1>{{ pet().name }}</h1>
    <p>Breed: {{ pet().breed }} </p>
    <p>Gender: {{ pet().gender }}</p>
  </div>
</template>

<script>
import { mapState } from 'vuex'

export default {
  data () {
    return {}
  },
  computed: {
    ...mapState([
      'cats',
      'dogs'
    ])
  },
  methods: {
    pet () {
      const animal = this[this.$route.params.species][this.$route.params.id]
      return animal
    }
  }
}
</script>
