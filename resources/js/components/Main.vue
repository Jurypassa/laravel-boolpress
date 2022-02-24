<template>
    <main>
        <h2>sono il main</h2>

        <ul>
            <li v-for="post in posts" :key="post.id">
                <p>{{post.title}}</p>
            </li>
        </ul>
    </main>
</template>

<script>
export default {
    name: "Main",
    data() {
        return {
            posts: []
        }
    },
    created(){
        axios.get("/api/posts")
        .then( (response) => {
            this.posts = response.data;
        } )
    }
}
</script>

<style>

</style>