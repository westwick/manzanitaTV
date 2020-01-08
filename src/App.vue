<template>
  <div id="app">
    <h2>My List</h2>
    <div class="my-list">
      <Title v-for="title in myList"
        :key="title.id"
        :title="title.title"
        :image="title.img"
      >
      </Title>
    </div>
    <h2>Recommendations</h2>
    <div class="recommendations">
      <Title v-for="title in myList"
        :key="title.id"
        :title="title.title"
        :image="title.img"
      >
      </Title>
    </div>
  </div>
</template>

<script>
import Title from './components/Title.vue';
import mockdata from './data/mockdata.json';

export default {
  name: 'app',
  data() {
    return {
      myList: mockdata.mylist,
      recommendations: mockdata.recommendations,
    };
  },
  components: {
    Title,
  },
};
</script>

<style lang="scss">
body {
  background: #f8f8f8;
  padding: 0 16px;
}
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  color: #2c3e50;
}
.my-list, .recommendations {
  display: flex;
}
</style>
