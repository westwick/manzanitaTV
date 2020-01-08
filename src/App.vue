<template>
  <div id="app">
    <HelloWorld msg="Welcome to Your Vue.js App"/>
    <h2>My List</h2>
    <div class="my-list">
      <div class="title" v-for="title in myList" :key="title.id">
        <img :src="title.img" />
        <p>{{title.title}}</p>
      </div>
    </div>
    <h2>Recommendations</h2>
    <div class="recommendations">
      <div class="title" v-for="title in recommendations" :key="title.id">
        <img :src="title.img" />
        <p>{{title.title}}</p>
      </div>
    </div>
  </div>
</template>

<script>
import HelloWorld from './components/HelloWorld.vue';
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
    HelloWorld,
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

.title {
  display: flex;
  flex-direction: column;
  margin-right: 32px;
}
</style>
