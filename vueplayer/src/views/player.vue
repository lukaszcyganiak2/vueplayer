<template>
  <v-card class="mx-auto">
    <v-list-item>
      <v-list-item-avatar color="grey"></v-list-item-avatar>
      <v-list-item-content>
        <v-list-item-title class="headline">Our Changing Planet</v-list-item-title>
        <v-list-item-subtitle>by Kurt Wagner</v-list-item-subtitle>
      </v-list-item-content>
    </v-list-item>

    <v-img class="main-img" :src="artist.image"></v-img>
    <div class="desctription">
      <p class="font-weight-bold main-p">{{artist.artist}}</p>
      <p class="font-weight-regular">{{artist.title}}</p>
    </div>

    <v-card-text>
      Visit ten places on our planet that are undergoing the biggest changes
      today.
    </v-card-text>

    <v-card-actions>
      <v-btn text color="deep-purple accent-4">Read</v-btn>
      <v-btn text color="deep-purple accent-4">Bookmark</v-btn>
      <v-spacer></v-spacer>
      <v-btn icon class="favorite" v-if="artist.favorite">
        <v-icon>mdi-heart</v-icon>
      </v-btn>

      <v-btn icon>
        <v-icon>mdi-share-variant</v-icon>
      </v-btn>
    </v-card-actions>
  </v-card>
</template>

<script>
export default {
  name: "App",

  data() {
    return {
      icon1: "fas fa-redo-alt"
    };
  },
  props: {
    artist: {
      type: Object,
      default: {}
    }
  },

  methods: {}
};
</script>

<style lang="scss" scoped>
.desctription {
  height: auto;
  color: red;
  padding: 10px;
  background-color: #4caf50;
  opacity: 0.1;
  .main-p {
    z-index: 1;
  }
  .favorite {
    color: red;
  }
}
</style>
