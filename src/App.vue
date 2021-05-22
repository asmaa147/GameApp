<template>
  <div id="app">

    <div class="row HeaderSection">
      <Header />
    </div>

    <div class="row CategorySection">
      <SliderCategory />
    </div>


    <router-view />
  </div>
</template>

<script>
import Header from "./components/Header.vue";
import SliderCategory from "./components/SliderCategory.vue";


export default {
  name: "Home",
  components: {
    Header,
    SliderCategory,
  },
};
</script>

<style>
*{
  padding: 0;
  margin: 0;
  box-sizing: border-box;
}
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  background-color: #f5f5f5;

}

.HeaderSection,
.CategorySection {
  background-color: #fff;
}

#nav {
  padding: 30px;
}

#nav a {
  font-weight: bold;
  color: #2c3e50;
}

#nav a.router-link-exact-active {
  color: #42b983;
}
</style>
