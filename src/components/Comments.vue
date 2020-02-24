<template>
  <div class="container">
    <h1>Comments</h1>
    <hr />

    <FormTodo v-on:add-todo="addComment"></FormTodo>
    
    <div v-for="(comment,index) in allComments" v-bind:key="index" class="list-grop-item">
      <span class="comment__author">
        Author:
        <Strong>{{ comment.name }}</Strong>
      </span>
      <p>{{ comment.message }}</p>
      <div>
        <a v-on:click.prevent="removeComment(index)" href="#" title="Delete">Delete</a>
      </div>
    </div>
    <hr />
  </div>
</template>

<script>
import FormTodo from './FormTodo'

export default {
  components: {
    FormTodo
  },
  data() {
    return {
      comments: [],
    };
  },
  methods: {
    addComment(comment) {
      this.comments.push(comment)
    },
    removeComment(index) {
      this.comments.splice(index, 1);
    }
  },
  computed: {
    allComments() {
      return this.comments.map(comment => ({
        ...comment,
        name: comment.name.trim() === "" ? "Anonymous" : comment.name
      }));
    }
  }
};
</script>
