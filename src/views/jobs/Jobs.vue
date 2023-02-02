<template>
    <div class="content">
        <h1 class="heading">Posts</h1>
        <div v-for="post in posts" :key="post.id" v-if="posts.length">
            <router-link :to="{ name: 'jobsDetails', params: { id: post.id } }">
                <div class="post">{{ post.title }}</div>
            </router-link>
        </div>
        <div v-else>
            <p>Loading page...</p>
        </div>
    </div>
</template>

<script>
export default {
    data() {
        return {
            posts: []
        }
    },
    mounted() {
        fetch('https://jsonplaceholder.typicode.com/posts')
            .then(res => res.json())
            .then(data => this.posts = data)
            .catch(err => console.log(err.message))
    }
}

</script>

<style scoped>
.heading {
    margin: 0 0 1rem 0;
}

a {
    text-decoration: none;
    font-size: 20px;
}

.post {
    padding: 1rem;
    margin: .5rem;
    border-radius: 5px;
    background-color: #22223b;
    color: #ced4da;
    max-width: 800px;
    box-shadow: 0px 0px 15px #000;
}
</style>