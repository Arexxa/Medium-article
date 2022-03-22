<template>

  <h1>Post Details</h1>
  <!-- <h2>{{ id }}</h2> -->
  <h3>{{ title }}</h3>
  <p>{{ details }}</p>

  <div class="form">
    <h2>Comment Section</h2>
    <input type="text" placeholder="Name" v-model="name" /><br>
    <input type="text" placeholder="Comment" v-model="comment" /><br>
    <button @click="addComment" class="submit">Submit</button>
  </div>
</template>

<script>
export default {
    name: 'PostDetails',
    props: ['id'],
    data() {
        return {
            id: this.$route.params.id,
            title: this.$route.params.title,
            details: this.$route.params.details,
            name: "",
            comment: "",
        }
    },
    methods: {
      addComment() {
        if(this.comment){
          this.comment.push({
            comment: this.comment,
          });
          this.comment = "";
        }
      }
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