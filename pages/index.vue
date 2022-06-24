<template>
  <div>
    <div v-for="post in posts" :key="post.id">
      <Post :title="post.title.rendered" :body="post.content.rendered" /><br>
    </div>
  </div>
</template>


<script>
  export default {
    data: () => ({
      posts: []
    }),
    async asyncData({ $axios }) {
      const posts = await $axios.$get('https://peabiru.org.br/wp-json/wp/v2/posts')

      console.log(posts)
      return { posts }
    }
  }
</script>
