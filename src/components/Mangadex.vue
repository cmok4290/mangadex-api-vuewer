<template>
  <div class="container">
    <h1>Mangadex API Vuewer</h1>
    <table class="table">
      <thead>
        <tr>
          <th scope="col">Title</th>
          <th scope="col">Updated</th>
          <th scope="col">Status</th>
        </tr>
      </thead>
      <tbody>
        <tr v-for="manga in mangalist" v-bind:key="manga.id">
          <th scope="row">{{ manga.data.attributes.title.en }}</th>
          <td>{{ manga.data.attributes.updatedAt }}</td>
          <td>{{ manga.data.attributes.status }}</td>
        </tr>
      </tbody>
    </table>
  </div>
</template>

<script>
import axios from "axios";
export default {
  name: "Mangadex",
  data() {
    return {
      mangalist: null,
    };
  },
  created: function () {
    axios.get("https://api.mangadex.org/manga").then((res) => {
      this.mangalist = res.data.results;
    });
  },
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped lang="scss">
h3 {
  margin: 40px 0 0;
}
ul {
  list-style-type: none;
  padding: 0;
}
li {
  display: inline-block;
  margin: 0 10px;
}
a {
  color: #42b983;
}
</style>
