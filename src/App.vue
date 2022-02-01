<template>
  <div id="app">
    <header-box
      :discsList="discs"
      :loadingValue="loading"
      :genreProp="genreList"
      @search="filterResult"
    />
    <main-container :discsList="discsFiltered" />
  </div>
</template>

<script>
import axios from "axios";
import HeaderBox from "./components/HeaderBox.vue";
import MainContainer from "./components/MainContainer.vue";

export default {
  name: "App",
  components: {
    HeaderBox,
    MainContainer,
  },
  data() {
    return {
      discs: [],
      discsFiltered: [],
      loading: true,
      genreList: [],
    };
  },
  mounted() {
    axios
      .get("https://flynn.boolean.careers/exercises/api/array/music")
      .then((response) => {
        this.discs = response.data.response;
        this.discsFiltered = response.data.response;
        this.loading = false;
        this.genreFilter();
        console.log(this.genreList);
      });
  },
  methods: {
    filterResult(keyword) {
      if (keyword === "all") {
        this.discsFiltered = this.discs;
      } else {
        this.discsFiltered = this.discs.filter((disc) => {
          return disc.genre.toLowerCase().includes(keyword);
        });
      }
    },
    genreFilter() {
      this.genreList = this.discs.filter((disc) => {
        if (!this.genreList.includes(disc.genre)) {
          return this.genreList.push(disc.genre);
        }
      });
    },
  },
};
</script>

<style lang="scss">
@import "./style/main.scss";
</style>
