<template>
    <main>
        <h3>Nome posts</h3>
        <ul>
            <li v-for="post in posts" :key="post.id">
                {{post.title}}
            </li>
        </ul>
    </main>
</template>

<script>
    export default {
        name: "Main",
        data() {
            return {
                posts: [],
            }
        },
        created() {
            axios.get("/api/posts")
                .then( (response) => {
                    this.posts = response.data;
                })
        }
    }
</script>

<style>

</style>