<template> </template>

<script>
import axios from "axios";
export default {
  name: "App",

  components: {},

  data() {
    return {
      artists: ""
    };
  },
  created: function() {
    this.getArtists();
  },
  methods: {
    getArtists() {
      fetch("18.185.121.3:5000")
        .then(res => console.log(JSON.parse(res)))
        .then(res => {
          console.log(JSON.parse(res));
        });
    }
  }
};
</script>

<style lang="scss" scoped></style>
