<template>
  <div class="featuredSection container">
    <b-row >
      <b-col cols="12" md="8">
        <b-img
          :src="RandomItem.thumbnail"
          fluid
          class="mb-2 w-100 img-fluid"
          style="height : 15em "
        ></b-img>
      </b-col>

      <b-col cols="12" md="4">
        <b-card-body>
          <b-card-title>
            {{ RandomItem.title }}
          </b-card-title>
          <b-card-text class="my-3">
            {{ RandomItem.short_description }}
          </b-card-text>
          <b-button class="my-3"> Read More </b-button>
        </b-card-body>
      </b-col>
    </b-row>
  </div>
</template>

<script>
export default {
  name: "FeaturedSection",
  props: {
    RandomItem: Object,
  },
};
</script>

<style scoped>
.featuredSection {
  width: 75%;
  padding: 1em;
  background-color: #fff;
  box-shadow: 0 4px 15px 5px rgba(0, 0, 0, 0.07);
}

</style>
