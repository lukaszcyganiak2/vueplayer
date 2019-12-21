<template>
  <div class="allView">
    <player></player>
    <playList></playList>
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

  data: () => ({
    //
  })
};
</script>

<style lang="scss" scoped>
.allView {
  margin: 0 auto;
  width: 80%;
  display: grid;
  grid-template-columns: auto auto;
  background-image: url("./assets/free psd(1).png");
  background-size: cover;
}
</style>
