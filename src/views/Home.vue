<template>
  <div class="home container-fluid">
    <div class="row my-3">
      <FeaturedSection :RandomItem="posts | randomItem" />
    </div>

    <div class="row w-75 mx-auto">
      <GameListSection
        :SectionTitle="' Most Recommendation  '"
        :posts="posts | firstItems"
      />
    </div>

    <div class="row my-3 w-75 mx-auto">
      <GameListSection
        :SectionTitle="' Most Popular '"
        :posts="posts | lastItems"
      />
    </div>
  </div>
</template>

<script>
import GameListSection from "../components/GameListSection.vue";
import FeaturedSection from "../components/FeaturedSection.vue";

// import json from "../json/db.json";

export default {
  name: "Home",
  components: {
    GameListSection,
    FeaturedSection,
  },

  data: function () {
    return {
      posts: [],
    };
  },
  filters: {
    firstItems: function (v) {
      return v.slice(0, 4);
    },
    lastItems: function (v) {
      return v.slice(5, 9);
    },
    randomItem: function (v) {
      return v[Math.floor(Math.random() * v.length)];
    },
  },

  created() {
    fetch(
      "https://free-to-play-games-database.p.rapidapi.com/api/filter?tag=3d.mmorpg.fantasy.pvp&platform=pc",
      {
        method: "GET",
        headers: {
          "x-rapidapi-key":
            "64dc64269bmsh61c0163afabfcdap12c739jsn35755ae3bbce",
          "x-rapidapi-host": "free-to-play-games-database.p.rapidapi.com",
        },
      }
    )
      .then((response) => response.json())
      .then((data) => this.posts = data)
      .catch((err) => {
        console.error(err);
      });
  },
};
</script>

<style scoped>
.home {
  width: 100%;
  /* border: 2px solid #000; */
  background-color: #f5f5f5;
}
</style>
