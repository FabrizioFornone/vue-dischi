<template>
  <main>
    <div class="container">
      <div class="d-flex flex-wrap">
        <div
          class="disc-box mt-5 text-center"
          v-for="(album, index) in discsList"
          :key="index"
        >
          <album-box :albumDisc="album" />
        </div>
      </div>
    </div>
  </main>
</template>

<script>
import AlbumBox from "./AlbumBox.vue";
export default {
  components: { AlbumBox },
  props: {
    discsList: Array,
  },
};
</script>

<style lang="scss" scoped>
@import "@/style/mainContainer.scss";
</style>
