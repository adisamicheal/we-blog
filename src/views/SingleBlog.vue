<template>
  <div class="post_body font">
      <div v-if="blog.length != 0 && comments.length != 0">
        <div class="post">
            <h3>{{blog.title | capitalize}}</h3>
            <p>{{blog.body | capitalize}}</p>
        </div>
        <p class="title">Comments <img src="../assets/comment.svg" alt="comment"></p>
        <div class="comments">
            <div class="comment" v-for="comment in comments" :key="comment.id">
                <p class="email">{{comment.email}}</p>
                <p class="name">{{comment.name | capitalize}}</p>        
                <p class="body">{{comment.body | capitalize}}</p>
                <hr>
            </div>
        </div>
      </div>
      <div v-else class="spinner">
        <div class="pixel-spinner">
         <div class="pixel-spinner-inner"></div>
        </div>
      </div>
  </div>
</template>

<script>
export default {
    name: 'SingleBlog',
    data() {
        return {
            id: this.$route.params.id,
            blog: {},
            comments: []
        }
    },
    mounted() {
        this.$http.get('https://jsonplaceholder.typicode.com/posts/' + this.id).then(
            response=> response.json()
        ).then(
            data => this.blog = data
        )
        this.$http.get('https://jsonplaceholder.typicode.com/comments?postId=' + this.id).then(
            response => response.json()
        ).then(
            data => {this.comments = data
            console.log(this.comments)}
        )
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
.post_body {
    padding: 50px;
    width: 60%;
    display: block;
    margin: auto;
}
.post h3 {
    font-size: 30px;
    font-weight: 600px;
}
.post p {
    font-size: 16px;
    line-height: 25px;
    margin-top: 20px;
}
.title {
    margin-top: 30px;
    font-size: 30px;
    font-weight: bolder;
    display: flex;
    align-items: center;
}
.title img {
    width: 30px;
    height: 30px;
    margin-left: 20px;
}
.comments {
    margin-top: 50px;
    border: 1px solid gray;
    padding: 20px;
}
.comment {
    margin-bottom: 20px;
}
.email {
    color: gray;
    font-size: 12px;
}
.name {
    font-weight: 600;
    font-size: 18px;
    margin-top: 20px;
}
.body {
    font-size: 16px;
    font-style: italic;
    font-weight: lighter;
    line-height: 25px;
}
hr {
    border: 1px solid gray;
    margin-top: 10px;
}
@media screen and (max-width: 768px) {
    .post_body {
        width: 90%;
        padding: 20px;
    }
}
</style>