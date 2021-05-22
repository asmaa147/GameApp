<template>
  <nav class="p-4">
    <ul class="categorySection nav justify-content-center">
      <li class="nav-item" :key="index" v-for="(catg, index) in Categories">
        <a
          class="nav-link"
          :class="catg == currentLink ? activeclass : ''"
          href="#"
        >
          {{ catg }}
        </a>
      </li>
    </ul>
  </nav>
</template>

<script>
export default {
  name: "SliderCategory",

  data: function () {
    return {
      Categories: ["Action", "Advanture", "Arcade", "Sports"],
      currentLink: "Sports",
    };
  },
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
.categorySection li a {
  color: #545454;
  border: 1px solid #d2d2d2;
  border-radius: 15px;
  padding: 4px 16px 6px 14px !important;
  box-shadow: 0 3px 10px 0 rgb(0 0 0 / 9%) ;
  margin: 10px;
  font-size: 14.4px;
}
.categorySection li a:hover {
  background-color: #572589;
  color:#fff;
}
.activeclass {
  background-color: #572589;
}
</style>
