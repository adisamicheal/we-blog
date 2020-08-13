<template>
    <div class="font base">
        <h3>Available blogs for the day! 😊</h3>
        <div class="blog_body">
            <div  v-if="blogPosts.length != 0">
                <div class="blog" v-for="blogPost in blogPosts" :key="blogPost.id">
                    <router-link :to="{ name: 'SingleBlog', params: { id: blogPost.id } }">
                        <div class="blog_link">
                            <img src="../assets/portfolio.svg" alt="pen-icon"> <p>{{ blogPost.title | capitalize}}</p>
                        </div>
                    </router-link>
                </div>
            </div>
            <div v-else class="spinner">
                <div class="pixel-spinner">
                <div class="pixel-spinner-inner"></div>
                </div>
            </div>
        </div>
    </div>
</template>

<script>
export default {
    name: 'AllBlogs',
    data() {
        return {
            blogPosts: []
        }
    },
    mounted() {
        this.$http
        .get("https://jsonplaceholder.typicode.com/posts/?_limit=60")
        .then((response) => response.json())
        .then((data) => (this.blogPosts = data));
        // console.log(response.json());
    },
    filters: {
        capitalize: function (value) {
            if (!value) return ''
            value = value.toString()
            return value.charAt(0).toUpperCase() + value.slice(1)
        }
    }
}
</script>

<style scoped>
.base {
    background: url(../assets/bg.svg);
    background-size: contain;
    /* height: 100vh; */
}
h3 {
    text-align: center;
    padding: 30px 0;
    font-size: 24px;
    font-weight: 600;
}
.blog_body {
    display: block;
    margin: auto;
    border: 2px solid #000000;
    padding: 20px 50px;
    width: 60%;
    margin-top: 10px;
    margin-bottom: 10px;
    background: #ffffff;
    /* height: 100vh; */
}
.blog {
    margin-bottom: 20px;
    border: 2px solid #000000;
    padding: 10px;
}
.blog:hover {
    background: #041705;
    transition: all ease-in-out 500ms;
}
.blog:hover a>.blog_link>p {
    color: #ffffff;
    transition: all ease-in-out 500ms;
}
.blog:hover a>.blog_link>img {
    filter: brightness(0) invert(1);
    transition: all ease-in-out 500ms;
}
.blog img {
    width: 30px;
    height: 30px;
    margin-right: 20px;
}
.blog a {
    text-decoration: none;
    font-size: 16px;
    font-weight: 400;
    color: #000000;
}
.blog_link {
    display: flex;
    align-items: center;
}
@media screen and (max-width: 768px) {
    .blog_body {
        width: 90%;
    }
}
</style>>
