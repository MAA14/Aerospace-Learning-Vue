<template>
  <div class="imgContainer" :class="className ?? ''" :id="idName ?? ''">
    <img :src="src" :alt="alt" />
  </div>
</template>

<script>
export default {
  name: 'Image',
  props: {
    src: String,
    alt: String,
    className: String,
    idName: String,
  },
};
</script>

<style>
.imgContainer img {
  width: 100%;
  height: 100%;
  object-fit: contain;
}
</style>
