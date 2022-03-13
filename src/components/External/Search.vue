<template>
  <div>
    <h1>BookList</h1>
    <input type="text" v-model="title"/>
    <div
      class="card my-3"
      style="width: 18rem"
      v-for="(book, index) in filteredBooks"
      v-bind:key="index"
    >
      <!-- <img src="..." class="card-img-top" alt="..." /> -->
      <div class="card-body">
        <h5 class="card-title">{{ book.title }}</h5>
        <p class="card-text">
          <ul>
            <li>Author: {{book.author}}</li>
            <li>Country: {{book.country}}</li>
            <li>Language: {{book.language}}</li>
          </ul>
        </p>
        <a href="#" class="btn btn-primary">Go somewhere</a>
      </div>
    </div>
  </div>
</template>

<script>
import axios from "axios";

export default {
  data: function () {
    return {
      library: [],
      title: "",
    };
  },
  created: async function () {
    // use axios to read in the content of the json file
    let response = await axios.get(
      "https://raw.githubusercontent.com/benoitvallon/100-best-books/master/books.json"
    );
    this.library = response.data;
  },
  computed: {
    filteredBooks: function () {
      let filtered = this.library.filter(
        (eachBook) =>
          eachBook.title.toLowerCase().includes(this.title.toLowerCase()) ||
          eachBook.author.toLowerCase().includes(this.title.toLowerCase())
      );
      return filtered;
    },
  },
};
</script>