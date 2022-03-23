<template>

  <h1>Post Details</h1>
  <!-- <h2>{{ id }}</h2> -->
  <h3>{{ title }}</h3>
  <p>{{ details }}</p>

  <comment-box ></comment-box>
  
</template>

<script>
import CommentBox from '../components/CommentBox.vue'

export default {
    name: 'PostDetails',
    props: ['id'],
    components: {
      CommentBox
    },

    data() {
        return {
            id: this.$route.params.id,
            title: this.$route.params.title,
            details: this.$route.params.details,
        }
    }
}
</script>

<style>

</style>