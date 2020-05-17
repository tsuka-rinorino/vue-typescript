<template>
  <div id="app">
    <Post :post="post"/>
  </div>
</template>


<script lang="ts">
import { Component, Vue } from 'vue-property-decorator';
import axios from 'axios';
import Post from '@/components/Post.vue';
import PostData from '@/interface/post.d';


@Component({
  components: {
    Post,
  },
})
export default class App extends Vue {
  public post: PostData = {
    title: '',
  };

  public endpoint = '/sample-data.json';

  created() {
    this.getPost();
  }

  public getPost() {
    axios.get(this.endpoint)
      .then((response) => {
        this.post = response.data;
      });
  }
}
</script>


<style lang="scss">
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
