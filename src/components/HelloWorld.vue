<template>
  <section>
    <div v-for="propertie in properties" :key="propertie.id">{{ propertie.seller.name }}</div>
  </section>
</template>

<script>
import gql from "graphql-tag";

export default {
  name: "HelloWorld",
  props: {
    msg: String
  },
  apollo: {
    properties: gql`
      query {
        properties {
          id
          district {
            id
            name
          }
          price
          rooms
          seller {
            id
            name
            email
          }
        }
      }
    `
  }
};
</script>