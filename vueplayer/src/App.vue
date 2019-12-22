<template>
  <div class="allView">
    <player :artist="artist"></player>
    <playList @artist="oneArtist"></playList>
  </div>
</template>

<script>
import player from "./views/player";
import playList from "./views/playList";
export default {
  name: "App",

  components: {
    player,
    playList
  },

  data() {
    return {
      artist: {}
    };
  },
  methods: {
    oneArtist(val) {
      this.artist = val;
    }
  }
};
</script>

<style lang="scss" scoped>
.allView {
  margin: 0 auto;
  width: 80%;
  display: grid;
  grid-template-columns: 50% 50%;
  background-image: url("./assets/free psd(1).png");
  background-size: cover;
}
</style>
