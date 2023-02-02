<template>
    <div v-if="post">
        <h1>{{ post.title }}</h1>
        <p>{{ post.body }}</p>
    </div>
    <div v-else>
        <p>Loading page...</p>
    </div>
</template>

<script>
export default {
    data() {
        return {
            id: this.$route.params.id,
            post: null
        }
    },
    mounted() {
        fetch('https://jsonplaceholder.typicode.com/posts/' + this.id)
            .then(res => res.json())
            .then(data => this.post = data)
            .catch(err => console.log(err.message))
    }
}

</script>

<style scoped>

</style>