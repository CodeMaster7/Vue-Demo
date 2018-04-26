<template>
  <div id="app">
    <h1>My Blogging App!</h1>
    <button @click='toggle(false)'>New Post</button>
    <button @click='toggle(true)'>Show All Posts</button>
    <section v-show='!showPosts'>
      <form>
        <h4>Create New Post:</h4>
        <textarea name="" id="" cols="90" rows="7"></textarea>
        <br>
        <button type='submit'>Add New Post</button>
      </form>
    </section>
    <section v-show='showPosts'>
    <h4>All Posts:</h4>
      <div v-for='(post,i) in posts' :key='i'>
        <p>Data: {{post.date}}</p>
        <p>Message: {{post.message}}</p>
        <hr>
      </div>
    </section>
  </div>
</template>

<script>
export default {
  data() {
    return {
      showPosts: true,
      posts: [{ date: new Date(), message: "test post" }]
    };
  },
  methods: {
    toggle(bool) {
      this.showPosts = bool
    }
  }
};
</script>

<style>

</style>
