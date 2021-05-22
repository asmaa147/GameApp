<template>
  <div class="DetailsPage container-fluid">
    <div class="DetailSection row my-3">
      <div class="row">
        <img
          :src="selectedItem.thumbnail"
          :alt="selectedItem.title"
          style="height: 20em"
        />
      </div>

      <div class="row">
        <b-card class="my-4">
          <b-card-body>
            <b-card-title>
              {{ selectedItem.title }}
            </b-card-title>

            <b-card-text>
              {{ selectedItem.short_description }}
            </b-card-text>
          </b-card-body>
        </b-card>
      </div>
    </div>

    <div class="row w-100">
      <GameListSection
        :SectionTitle="' Most Recommendation  '"
        :posts="posts | firstItems"
      />
    </div>
  </div>
</template>

<script>
// import json from "../json/db.json";

import GameListSection from "../components/GameListSection.vue";

export default {
  name: "DetailsPage",
  data() {
    return {
      posts: [],
      selectedItem: {},
    };
  },

  components: {
    GameListSection,
  },
    filters: {
    firstItems: function (v) {
      return v.slice(0, 5);
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
      .then((data) =>  {this.posts = data ;
             this.selectedItem = data[this.$route.params.id - 1]})
      .catch((err) => {
        console.error(err);
      });
  },
};
</script>

<style scoped>
.DetailsPage {
  width: 75%;
  padding: 1em;
  margin: auto;
  /* box-shadow: 0 4px 15px 5px rgba(0, 0, 0, 0.07); */
}
</style>
