<template>
  <div class="single-album my-2 py-2">
    <a href="#">
      <img class="py-1" :src="albumDisc.poster" alt="" />
      <div class="py-1 fs-4 fw-bold text-white">{{ albumDisc.title }}</div>
      <div class="text-secondary">{{ albumDisc.author }}</div>
      <div class="text-secondary">{{ albumDisc.year }}</div>
    </a>
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
