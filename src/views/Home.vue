<template>
  <div class="home">
    <Mangadex />
  </div>
</template>

<script>
// @ is an alias to /src
import Mangadex from "@/components/Mangadex.vue";

export default {
  name: "Home",
  components: {
    Mangadex,
  },
};
</script>
