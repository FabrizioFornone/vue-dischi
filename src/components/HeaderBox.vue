<template>
  <header>
    <div class="mx-3 py-2 d-flex justify-content-between">
      <div class="d-flex align-item-center">
        <img class="" src="@/assets/logo-small.svg" alt="" />
        <select
          class="mx-5 px-3"
          name=""
          @change="$emit('search', selected)"
          v-model="selected"
        >
          <option value="all">All</option>
          <option v-for="(discGenre, index) in genreProp" :key="index" :value="discGenre.genre.toLowerCase()">{{discGenre.genre}}</option>
        </select>
      </div>
      <loader v-if="loadingValue" />
    </div>
  </header>
</template>

<script>
import Loader from "./Loader.vue";
export default {
  components: { Loader },
  props: {
    discsList: Array,
    loadingValue: Boolean,
    genreProp: Array,
  },
  data() {
    return {
      selected: "all",
    };
  },
};
</script>

<style lang="scss" scoped LoaderComponent>
@import "@/style/headerBox.scss";
</style>
