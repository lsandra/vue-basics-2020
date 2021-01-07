<template>
  <div>
    <h1>TEST</h1>
    <ul class="-table">
      <li
        class="anime-list-item"
        v-for="anime in anime"
        :key="anime.name"
      >
        {{ anime.name }}
      </li>
    </ul>
  </div>
</template>

<script>
export default {
  name: "anime",
  data() {
    return { anime: [] };
  },
  props: ["id", "offset"],
  mounted: function() {
    this.fetchData();
  },
  methods: {
    fetchData: async function() {
      try {
        const result = await fetch(
          `https://pokeapi.co/api/v2/pokemon?limit=${this.id}&offset=${this.offset}`
        );
        const data = await result.json();
        console.log(data);
        this.pokemons = data.results;
      } catch (error) {
        alert(error);
      }
    },
  },
};
</script>

<style>
h1 {
  font-size: 5rem;
  color: white;
}
li {
  color: white;
}
</style>