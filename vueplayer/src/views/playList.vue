<template>
  <v-card max-width="600" class="mx-auto">
    <v-toolbar-title>
      <i class="fas fa-undo" @click="a"></i>
      Play List
    </v-toolbar-title>

    <v-spacer></v-spacer>

    <v-list two-line subheader>
      <v-list-item v-for="(item, index) in artists" :key="index">
        <v-list-item-content @click="handlerArtist(item)">
          <v-list-item-subtitle v-text="item.time + ' ' + item.artist"></v-list-item-subtitle>
          <v-list-item-title v-text="item.title"></v-list-item-title>
        </v-list-item-content>
        <v-list-item-action>
          <i class="fas fa-share-alt"></i>
        </v-list-item-action>
        <v-list-item-action v-if="item.favorite">
          <v-btn icon @click="a(item)">
            <i class="fas fa-heart favorite"></i>
          </v-btn>
        </v-list-item-action>
        <v-list-item-action v-else>
          <v-btn icon @click="a(item)">
            <i class="fas fa-heart"></i>
          </v-btn>
        </v-list-item-action>
      </v-list-item>
    </v-list>
  </v-card>
</template>

<script>
export default {
  data() {
    return {
      artists: [
        {
          artist: "Icona Pop",
          favorite: true,
          image: "https://i.ytimg.com/vi/3TDHRSjR0s0/maxresdefault.jpg",
          time: "2:35",
          title: "Still Don't Know"
        },
        {
          artist: "Icona Pop",
          favorite: false,
          image: "https://i.ytimg.com/vi/HQ40wBhB4dc/hqdefault.jpg",
          time: "3:20",
          title: "I Love it"
        },
        {
          artist: "Icona Pop",
          favorite: true,
          image: "https://i.ytimg.com/vi/4_7zkXv17QE/maxresdefault.jpg",
          time: "2:51",
          title: "Nights Like This"
        },
        {
          artist: "Icona Pop",
          favorite: false,
          image:
            "https://bi.im-g.pl/im/29/ab/14/z21672489V,W-Gdansku-rozpoczal-sie-jeden-z-najpopularniejszyc.jpg",
          time: "3:02",
          title: "We Got the World"
        }
      ]
    };
  },
  created: function() {
    this.getArtists();
  },
  methods: {
    getArtists() {
      try {
        fetch("18.185.121.3:5000")
          .then(res => res.json())
          .then(res => {
            if (res) {
              this.artists = res;
            }
          });
      } catch {
        console.log("error");
      }
    },
    a(item) {
      this.artists.forEach(art => {
        if (art.title == item.title) {
          art.favorite = !art.favorite;
        }
      });
    },
    handlerArtist(artist) {
      this.$emit("artist", artist);
    }
  }
};
</script>
<style lang="scss" scoped>
.favorite {
  color: red;
}
</style>
