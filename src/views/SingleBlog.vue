<template>
  <div class="post_body font">
      <div v-if="blog.length != 0 && comments.length != 0">
        <div class="post">
            <h3>{{blog.title | capitalize}}</h3>
            <img src="../assets/blog-read.jpg" alt="blog-image">
            <p>{{blog.body | capitalize}}</p>
        </div>
        <p class="title">Comments <span>({{this.getTotalComments}})</span> <img src="../assets/comment.svg" alt="comment"></p>
        <div class="comments">
            <div class="comment" v-for="comment in comments" :key="comment.id">
                <img src="../assets/user.svg" alt="user"> <p class="email">{{comment.email}}</p>
                <p class="name">{{comment.name | capitalize}}</p>        
                <p class="body">{{comment.body | capitalize}}</p>
                <hr>
            </div>
        </div>
        <div class="form">
            <h2>Add a comment</h2>
            <form action="" @submit.prevent="onSubmit">
                <div class="flex">
                    <label for="name">Your Name</label>
                    <input type="text" name="" id="" v-model="newComment.name">
                </div>
                <div class="flex">
                    <label for="name">Your Email</label>
                    <input type="text" name="" id="" v-model="newComment.email">
                </div>
                <div class="flex">
                    <label for="comment">Your Comment</label>
                    <!-- <input type="text" name="" id=""> -->
                    <textarea name="comment" id="" cols="30" rows="10" v-model="newComment.body"></textarea>
                </div>
                <div v-if="showError" class="error">Please fill all fields.</div>
                <div class="button">
                    <button>Submit</button>
                </div>
            </form>
        </div>
      </div>
      <div v-else class="spinner">
        <div class="pixel-spinner">
         <div class="pixel-spinner-inner"></div>
        </div>
      </div>
  </div>
</template>
9
<script>
export default {
    name: 'SingleBlog',
    data() {
        return {
            id: this.$route.params.id,
            blog: {},
            comments: [],
            newComment: {
                name: '',
                email: '',
                body: ''
            },
            showError: false,
            // formComplete: false
        }
    },
    watch: {
        newComment: () => {
            if (this.newComment.name && this.newComment.email && this.newComment.body) {
                this.showError = false
            }
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
            // console.log(this.comments)
            }
        )
    },
    computed: {
        getTotalComments() {
            var cnt = 0;
            var arr = this.comments;
    
            arr.forEach(function(itm){
            if(!itm.__proto__.__proto__) {
                cnt++;
            }
            });
            return cnt
        },
    },
    methods: {
        onSubmit() {
            if(!(this.newComment.name && this.newComment.email && this.newComment.body)) {
                this.showError = true
            }
            if (this.newComment.name && this.newComment.email && this.newComment.body) {
                this.comments.push(this.newComment);
                this.newComment = {
                name: "",
                email: "",
                body: "",
                };
            }
        },
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
    /* height: 100vh; */
}
.post h3 {
    font-size: 30px;
    font-weight: 600px;
}
.post img {
    margin-top: 20px;
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
.title span {
    font-size: 16px;
    margin-left: 10px;
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
.comment img {
    width: 20px;
    height: 20px;
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
.form {
    padding: 50px;
}
.flex {
    display: flex;
    flex-direction: column;
    margin-top: 20px;
}
.flex label {
    margin-bottom: 10px;
}
.flex input {
    height: 40px;
    padding: 10px;
}
.flex textarea {
    padding: 10px;
}
.button button {
    padding: 5px 30px;
    border-radius: 10px;
    color: #ffffff;
    background: #041705;
    border: 2px solid #041705;
    cursor: pointer;
    margin-top: 30px;
}
.button button:hover {
    background: #ffffff;
    color: #041705;
    transition: all ease-in-out 200ms;
}
.error {
    color: #ffffff;
    background: red;
    padding: 5px;
    font-size: 14px;
    font-weight: 600;
    margin-top: 20px;
}
@media screen and (max-width: 768px) {
    .post_body {
        width: 90%;
        padding: 20px;
    }
    .post img {
        width: 100%;
    }
    .form {
        padding: 20px 0;
    }
}
</style>