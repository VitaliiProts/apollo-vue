<template>
  <section>
    <div v-for="allFilm in allFilms" :key="allFilm.id">{{ allFilm.director }}</div>
  </section>
</template>

<script>
import gql from 'graphql-tag';

export default {
  name: 'HelloWorld',
  props: {
    msg: String
  },
  apollo: {
    allFilms: gql`
      query {
        allFilms {
          id
          director
        }
      }
    `
  }
}
</script>