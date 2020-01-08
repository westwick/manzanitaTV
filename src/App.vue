<template>
  <div id="app">
    <h2>My List</h2>
    <div class="my-list">
      <p v-if="myList.length <= 0">No titles to display</p>
      <Title v-for="title in myList"
        :key="title.id"
        :title="title"
        :buttonText="'Remove'"
        @titleClicked="removeTitle(title)"
      >
      </Title>
    </div>
    <h2>Recommendations</h2>
    <div class="recommendations">
      <p v-if="recommendations.length <= 0">No recommendations, check back soon!</p>
      <Title v-for="title in recommendations"
        :key="title.id"
        :title="title"
        :buttonText="'Add'"
        @titleClicked="addTitle(title)"
      >
      </Title>
    </div>
    <p>Selected Titles ({{ myList.length }}): {{ selectedTitles }}</p>
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
  computed: {
    selectedTitles() {
      return this.myList.length ? this.myList.map(title => title.title).join(', ') : 'No titles selected';
    },
  },
  methods: {
    addTitle(titleToAdd) {
      if (!this.myList.includes(titleToAdd)) {
        this.myList.push(titleToAdd);
      } else {
        // what to do if title already in my list?
        // pop up a toast maybe?
      }
    },
    removeTitle(titleToRemove) {
      this.myList = this.myList.filter(title => title.id !== titleToRemove.id);
    },
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
