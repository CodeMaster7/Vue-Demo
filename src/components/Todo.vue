<template>
  <div>
    <p>Date: {{todo.date}}</p>
    <p>Message: {{todo.message}}</p>
    <hr>    
  </div>
</template>

<script>
export default {
  props: ['todo']
};
</script>

<style>

</style>