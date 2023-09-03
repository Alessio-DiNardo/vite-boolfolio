<template>
    <div>
        AppMain
    </div>
    <div>
        <p v-for="post in posts">
            {{post.title}}
        </p>
    </div>
</template>
<script>
import axios from 'axios';
export default {
    name: 'AppMain',

    data() {
        return {
            posts : [],
            apiUrl : 'http://127.0.0.1:8000/api/posts'
        }
    },

    methods: {
        getPosts(){
                axios.get(this.apiUrl, {
                    params: {}
                })
                .then(function (response) {
                    this.posts = response.data.results.data;
                })
                .catch(function (error) {
                    console.log(error);
                })
        }
    },
}
</script>
<style lang="scss">
    
</style>