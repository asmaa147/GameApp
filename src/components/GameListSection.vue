<template>
  <b-container class="GameList">
    <b-row align-h="between" align-v="center">
      <b-col cols="10">
        <h3 class="SectionTitle">{{ SectionTitle }}</h3>
      </b-col>
      <b-col>
        <span cols="2">
          SEE ALL
          <img src="../assets/arrow-right-short.svg" class="seeAllIcon" />
        </span>
      </b-col>
    </b-row>

    <b-row cols="5" >
      <b-col v-for="post in posts" :key="post.id">
        <b-card style="" class="mb-2">

          <router-link :to="'/DetailsPage/' + post.id">
            <b-card-img :src="post.thumbnail" :img-alt="post.title" img-top />
          </router-link>

          <b-card-title class="my-3"> 
           <h5> {{ post.title }} </h5> 
          </b-card-title>
          <b-card-text>
            {{ post.short_description | shorten }}
          </b-card-text>

          <b-button class="card-btn" href="#"> Read More </b-button>
        </b-card>
      </b-col>
    </b-row>
  </b-container>
</template>

<script>
export default {
  name: "GameListSection",
  props: {
    posts: Array,
    SectionTitle: String,
  },
  filters: {
    shorten: function (value) {
      return `${value.substring(0, 15)} ....`;
    },
  },
};
</script>

<style scoped>
.GameList {
  /* width: 76%; */
  padding: 1em;
  /* border: 2px solid #572589; */
  background-color: #fff;
  text-align: center;
  box-shadow: 0 4px 15px 5px rgba(0, 0, 0, 0.07);
}
.seeAllIcon {
  width: 25px;
  height: 30px;
  color: #572589;
}
.SectionTitle {
  font-size: 20px;
  color: #232222;
  margin: 1em 0;
  font-weight: bold;
  line-height: 1.56;
  letter-spacing: -0.2px;
  text-align: left;
}

.card-btn {
  background-color: #572589;
}
</style>
