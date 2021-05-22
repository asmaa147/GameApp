<template>
  <div class="header container">
    <div class="row">
      <b-row v-show="showLogin" v-b-visible="handleVisibility">
        <Login />
      </b-row>

      <b-row class="align-items-center px-0">
        <div class=" col-md-6 col-4 d-flex align-items-center">
          <router-link to="/">
            <img
              class="img-fluid"
              alt="game-store-logo"
              src="../assets/Logo.svg"
            />
          </router-link>
          <p class="title align-self-center">Game Store</p>
        </div>

        <div class=" col-md-6 col-8 d-flex flex-row-reverse align-items-center">
          <img
            class="moreIcon float-end"
            @click="showLogin = !showLogin"
            src="../assets/three-dots-vertical.svg"
            alt="dropdown panel"
          />

          <img
            class="searchIcon float-end"
            @click="showSearch = !showSearch"
            src="../assets/search.svg"
            alt="search area"
          />
          <b-form-input
            v-model="text"
            v-show="showSearch"
            v-b-visible="handleVisibility"
            placeholder="Type Your Search Here ...."
            class="searchInput mx-3"
          ></b-form-input>
        </div>
      </b-row>
    </div>
  </div>
</template>

<script>
import Login from "./Login.vue";
export default {
  name: "Header",

  data: function () {
    return {
      showLogin: false,
      showSearch: false,
      isVisible: false,
    };
  },

  methods: {
    handleVisibility(isVisible) {
      this.isVisible = isVisible;
    },
  },

  components: {
    Login,
  },
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
.header {
  width: 75%;
  position: relative;
  box-shadow: 0 3px 5px 0 rgb(0 0 0 / 9%) ;

}
div {
  height: 100%;
}
.title {
  color: #572589;
  font-size: 19px;
  font-family: Tajawal, Tohama;
  font-weight: bold;
  font-stretch: normal;
  font-style: normal;
}
.searchIcon {
  width: 16px;
  height: 15.3px;
  color: #572589;
}
.searchIcon:hover {
  color: #300c55;
}
.moreIcon {
  width: 22px;
  height: 21px;
  margin: 0 15px;
}
</style>
