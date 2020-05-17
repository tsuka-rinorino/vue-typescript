<template>
  <div class="post">
    {{ post.title }}
  </div>
</template>


<script lang="ts">
import { Component, Vue, Prop } from 'vue-property-decorator';
import PostData from '@/interface/post.d';

@Component
export default class Post extends Vue {
  @Prop()
  public post!: PostData;
}
</script>
