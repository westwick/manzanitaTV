<template>
  <div class="title">
    <div class="img-wrap">
      <img :src="title.img" />
      <button @click="handleClick(title)">{{ buttonText }}</button>
    </div>
    <p>{{ title.title }}</p>
  </div>
</template>

<script>
export default {
  name: 'Title',
  props: {
    title: Object,
    buttonText: String,
  },
  methods: {
    handleClick(title) {
      console.log('title clicked', title);
      this.$emit('titleClicked', title);
    },
  },
};
</script>


<style lang="scss">
.title {
  display: flex;
  flex-direction: column;
  margin-right: 32px;

  img {
    height: 220px;
    width: auto;
  }

  button {
    background: rgba(0,0,0,.67);
    display: none;
    padding: 0.35em 1.2em;
    border: 2px solid #111;
    box-sizing: border-box;
    text-decoration: none;
    color: #fff;
    text-align: center;
    position: absolute;
    text-transform: uppercase;
    font-size: 18px;
    font-weight: bold;
    width: 100%;
    bottom: 0;
    left: 0;
    cursor: pointer;
  }

  .img-wrap {
    position: relative;
    height: 220px;
    &:hover button {
      display: inline-block;
    }
  }
}
</style>
