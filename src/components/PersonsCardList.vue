<template>
  <div class="row row-cols-1 row-cols-md-4 g-4">
    <div class="col" v-for="person in persons" :key="person.id">
      <div class="card h-100">
        <img :src="getAvatar(person)" class="card-img-top" :alt="person.firstname + ' ' + person.lastname">
        <div class="card-body">
          <h5 class="card-title">{{ person.firstname }} {{ person.lastname }}</h5>
          <p class="card-text">
            {{ person.firstname }} {{ person.lastname }} ist {{ person.vaccinated ? 'geimpft' : 'nicht geimpft' }} und
            hat {{ person.pets.length }} Haustier(e).
          </p>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: 'PersonsCardList',
  props: {
    persons: {
      type: Array,
      required: true
    }
  },
  methods: {
    getAvatar (person) {
      if (person.gender === 'MALE') {
        return require('../assets/male.png')
      } else if (person.gender === 'FEMALE') {
        return require('../assets/Female.png')
      }
    }
  }
}
</script>

<style scoped>
</style>
