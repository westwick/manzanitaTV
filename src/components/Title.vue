<template>
  <div class="title">
    <img :src="image" />
    <p>{{ title }}</p>
  </div>
</template>

<script>
export default {
  name: 'Title',
  props: {
    title: String,
    image: String,
  },
};
</script>


<style lang="scss">
.title {
  display: flex;
  flex-direction: column;
  margin-right: 32px;
}
</style>
