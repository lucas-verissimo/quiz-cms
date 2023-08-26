<template>
  <div v-if="post">
    <h1>{{ post.title }}</h1>
    <div>{{ post.content }}</div>
  </div>
</template>

<script>
import Posts from '~/mockdata/posts.json'
export default {
  data() {
    return {
      post: null
    }
  },
  created() {
    const post = Posts.find(post => post.id === this.$route.params.id)
    if (post) this.post = post
  }
};
</script>
