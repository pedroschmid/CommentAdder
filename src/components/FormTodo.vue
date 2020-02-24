<template>
  <div class="form-todo form-group">
    <p>
      <input v-model="name" class="form-control" type="text" name="name" placeholder="Name" />
    </p>
    <p>
      <textarea v-model="message" class="form-control" name="message" placeholder="Message"></textarea>
    </p>
    <button v-on:click="addComment" class="btn btn-primary" type="submit">Comment</button>
  </div>
</template>

<script>
export default {
  data() {
    return {
      name: "",
      message: ""
    };
  },
  methods: {
    addComment() {
      if (this.message.trim() === "")
        return alert("The fields cannot be empty!");

      this.$emit('add-todo', {
        name: this.name,
        message: this.message
      })

      this.name = "";
      this.message = "";
    }
  }
};
</script>