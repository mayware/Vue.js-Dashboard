<template>
    <div>
        <h1>Jobs</h1>
        <div v-for="job in jobs" :key="job.id">
            <router-link :to="{ name: 'jobsDetails', params: { id: job.id } }">
                <h2>{{ job.title }}</h2>
            </router-link>
        </div>
    </div>
</template>

<script>
export default {
    data() {
        return {
            jobs: [
                { title: 'UX Designer', id: 1, details: 'ux designer' },
                { title: 'UI Designer', id: 25, details: 'ui designer' },
                { title: 'Web Designer', id: 3, details: 'web designer' }
            ]
        }
    }
}

</script>

<style  scoped>

</style>