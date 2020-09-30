<template>
<form v-on:submit.prevent="bookSubmit(bookData)" class="" action="#" method="post">
    <input type="text" name="title" value="" placeholder="Book Title" v-model="bookData.bookTitle">
    <input type="text" name="author" value="" placeholder="Book Author" v-model="bookData.bookAuthor">
    <div>

      <input v-model="bookData.finishedReading" type="checkbox" />
      <label for="finishedReading"> finished Reading </label>

     <input type="radio" id="borrowed" v-model="bookData.ownership"/>
     <label for="borrowed"> borrowed </label>

     <input type="radio" id="bought" v-model="bookData.ownership"/>
     <label for="bought"> bought </label>


    </div>
    <button type="submit" name="button">Add Book</button>
</form>
</template>

<script>
export default {
  name: 'BookForm',
  props: ['books'],

  data() {
    return {
      bookTitle: '',
      bookAuthor: '',

      bookData: {
        bookTitle: "",
        bookAuthor: "",
        finishedReading: fals,

        ownership: [],

      },
    };
  },


    methods: {
      bookSubmit(bookData) {
          this.$emit('addBook', bookData);

      },
    },

};
</script>

<style >

</style>
