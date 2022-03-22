<template>
    <h1>Post Page</h1>
    <div v-for="post in posts" :key="post.id" class="post">
        <router-link :to="{ name: 'PostDetails', params: { id: post.id, title: post.title, details: post.details }}">
            <h2>{{ post.title }}</h2>
        </router-link>
    </div>
</template>

<script>
// import PostDetails from './Post-details.vue'

export default {
    name: 'Post',
    // components: {
    //     PostDetails
    // },
    data() {
        return {
            posts: [
                { id: 1, title: 'First post', exerpt: 'This is first post', details: 'Lorem ipsum dolor sit amet consectetur, adipisicing elit.' },
                { id: 2, title: 'Second post', exerpt: 'This is second post', details: 'Lorem ipsum dolor sit amet consectetur, adipisicing elit.' },
                { id: 3, title: 'Third post', exerpt: 'This is third post', details: 'Lorem ipsum dolor sit amet consectetur, adipisicing elit.' },
            ] 
        }
    }
}
</script>

<style>
.post h2{
    background: #f4f4f4;
    padding: 20px;
    border-radius: 10px;
    margin: 10px auto;
    max-width: 600px;
    cursor: pointer;
    color: #444;
}
.post h2:hover {
    background: #ddd;
}
.post a{
    text-decoration: none;
}
</style>