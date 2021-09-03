<template>
  <form v-on:submit.prevent="bookSubmit(bookTitle, bookAuthor)" class="" action="#" method="post">
    <input v-model="bookData.bookTitle" type="text" name="title" value="" placeholder="Book Title">
    <input v-model="bookData.bookAuthor" type="text" name="author" value="" placeholder="Book Author">
    <input v-model="bookData.finishedReading" type="checkbox" name="finished">
    <label for="bookData.finishedReading" text="finished reading?"></label>
    <input v-model="bookData.ownership" type="radio" value="borrowed">
    <label for="borrowed" text="borrowed"></label>
    <input v-model="bookData.ownership" type="radio" value="brought">
    <label for="bought" text="bought"></label>

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
    bookSubmit(bookTitle, bookAuthor) {
      this.$emit("addBook", bookTitle, bookAuthor);
    }
  }
};
</script>

<style>
</style>
