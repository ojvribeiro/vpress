<template>
  <Post />
</template>


<script>
  export default {
    data: () => ({
      id: this.$route.params.id,
      post: {},
    }),

    computed: {
      id() {
        return this.$route.params.id
      },

      post() {
        return this.$store.state.posts.find(post => post.id === this.id)
      },
    },

    async mounted() {
      try {
        const post = await $axios.$get(`https://peabiru.org.br/wp-json/wp/v2/posts/${this.id}`)
        console.log(post)
      }
      catch (e) {
        console.error(e)
      }
    },
  }
</script>
