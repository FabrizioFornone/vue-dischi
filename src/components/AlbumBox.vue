<template>
  <div class="single-album">
    <img class="py-1" :src="albumDisc.poster" alt="" />
    <div class="py-1 fs-4 text-white">{{ albumDisc.title }}</div>
    <hr class="my-1" />
    <div class="py-1">{{ albumDisc.author }}</div>
    <div class="py-1">{{ albumDisc.year }}</div>
  </div>
</template>

<script>
export default {
  props: {
    albumDisc: Object,
  },
};
</script>

<style lang="scss" scoped>
@import "@/style/albumBox.scss";
</style>
