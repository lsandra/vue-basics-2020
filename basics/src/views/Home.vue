<template>
  <div class="home">
    <anime:id="20" :offset="0" />
  </div>
</template>

<script>
import anime from "../components/anime";
export default {
  name: "Home",
  components: {
    anime,
  },
};
</script>
