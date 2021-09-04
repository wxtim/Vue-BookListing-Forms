<template>
  <form v-on:submit.prevent="bookSubmit(bookData)" class="" action="#" method="post">
    <input v-model="bookData.bookTitle" type="text" name="title" value="" placeholder="Book Title">
    <input v-model="bookData.bookAuthor" type="text" name="author" value="" placeholder="Book Author">

    <label for="finishedReading">
      Finished Reading
      <input v-model="bookData.finishedReading" type="checkbox" name="finishedReading" value="">
    </label>

    <label for="borrowed" text="borrowed">
      borrowed
      <input v-model="bookData.ownership" type="radio" value="borrowed">
    </label>

    <label for="bought" text="bought">
      bought
      <input v-model="bookData.ownership" type="radio" value="brought">
    </label>

    <button type="submit" name="button">Add Book</button>
  </form>
</template>

<script>
export default {
  name: "BookForm",
  props: ["books"],
  data() {
    return {
      bookData: {
        bookTitle: "",
        bookAuthor: "",
        finishedReading: false,
        ownership: []
      }
    };
  },
  methods: {
    bookSubmit(bookData) {
      this.$emit("addBook", bookData);
    }
  }
};
</script>

<style>
</style>
