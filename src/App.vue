<template>
  <div id="app">
    <header-box :discsList="discs" :loadingValue="loading" />
    <main-container :discsList="discs" />
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
      loading: true,
    };
  },
  mounted() {
    axios
      .get("https://flynn.boolean.careers/exercises/api/array/music")
      .then((response) => {
        this.discs = response.data.response;
        this.loading = false;
      });
  },
};
</script>

<style lang="scss">
@import "./style/main.scss";
</style>
