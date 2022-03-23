<template>
  <div class="form">
    <h2>Comment Section</h2>
    <input type="text" placeholder="Name" v-model="name" /><br>
    <input type="text" placeholder="Comment" v-model="newComment" /><br>
    <button @click="addComment" class="submit">Submit</button>
  </div>

  <h2 v-for="(comment, index) in comments" :key="index">{{ comment }}</h2>
</template>

<script>

export default {
    name: 'CommentBox',
    data() {
        return {
            name: "",
            newComment: "",
            comments: []
        }
    },

    mounted() {
        this.loadComments('23')
    },

    methods: {
      addComment() {
        if(this.newComment){
          this.comments.push({
            comment: this.newComment,
          });
          this.newComment = "";
        }
      }
    },

    loadComments(id) {
        //load
    }
}
</script>

<style>

.form {
  padding: 30px;
  background: #a9c9ba;
  margin: 10px auto;
  max-width: 600px;
}

.form input{
  background: #f4f4f4;
  padding: 20px;
  border-radius: 10px;
  margin: 10px auto;
  max-width: 600px;
  color: #444;
}

.form button {
  padding: 5px;
  border-radius: 10px;
  font-weight: bold;
  color: #2c3e50;
  text-decoration: none;
  border-radius: 2px;
}

</style>