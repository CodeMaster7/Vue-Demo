<template>
  <div id="app">
    <h1>My Blogging App!</h1>
    <button @click='toggle(false)'>New Post</button>
    <button @click='toggle(true)'>Show All Posts</button>
    <!-- <section v-show='!showPosts'> -->
    <section v-if='!showPosts'>
      <form @submit.prevent='addPost'>
        <h4>Create New Post:</h4>
        <textarea name="" id="" cols="90" rows="7" v-model='userInput'></textarea>
        <br>
        <button type='submit'>Add New Post</button>
      </form>
    </section>
    <!-- <section v-show='showPosts'> -->
    <section v-else>
    <h4>All Posts:</h4>
     <todo 
      v-for='(todo, i) in posts'
      :key='i'
      :todo='todo'
     ></todo>
    </section>
  </div>
</template>

<script>
import Todo from "./components/Todo";
export default {
  data() {
    return {
      showPosts: true,
      posts: [{ date: new Date(), message: "test post" }],
      userInput: ""
    };
  },
  methods: {
    toggle(bool) {
      this.showPosts = bool;
    },
    addPost() {
      let newPost = {
        date: new Date(),
        message: this.userInput
      };
      this.posts.push(newPost);
      this.userInput = "";
      this.showPosts = true;
    }
  },
  components: {
    todo: Todo
    //dont use camel case, dont use capitals//
  },
  mounted() {
    console.log("mounted");
    // axios.get().then(res => {
    //   this.arr = res.data;
    // });
  }
};
</script>

<style>

</style>
