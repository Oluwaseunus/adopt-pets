<template>
  <div>
    <h1>{{ sentenceCaseSpecies }} for adoption</h1>
    <b-table striped hover :items="pets">
      <template slot="name" slot-scope="data">
        <router-link :to="`/pets/${species}/${data.index}`">{{ data.value }}</router-link>
      </template>
    </b-table>
  </div>
</template>

<script>
  export default {
    props: {
      species: String,
      pets: Array
    },
    computed: {
      sentenceCaseSpecies() {
        return this.species.charAt(0).toUpperCase() + this.species.slice(1);
      }
    }
  };
</script>