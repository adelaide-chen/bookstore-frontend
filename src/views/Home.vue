<template>
  <Books />
</template>

<script>
import Books from "../components/Books";

export default {
  name: 'home',
  components: {Books},
  data: () => ({
    items: [
      { title: 'Dashboard', icon: 'mdi-view-dashboard' },
      { title: 'Photos', icon: 'mdi-image' },
      { title: 'About', icon: 'mdi-help-box' },
    ],
    numItems: 0,
    selected: [],
    search: '',
    singleSelect: false,
    headers: [
      {
        text: 'Book Title',
        align: 'center',
        sortable: false,
        value: 'name'
      },
      { text: 'Author', align: 'center', value: 'author' },
      { text: 'ISBN', align: 'center', value: 'ISBN' },
      { text: 'Genre', align: 'center', value: 'genre' }
    ],
    books: [
      {
        name: 'Harry Potter and the Prisoner of Azkaban',
        author: 'JK Rowling',
        ISBN: '134238982734',
        genre: 'fantasy',
      },

      {
        name: 'Harry Potter',
        author: 'JK Rowling',
        ISBN: '134238982734',
        genre: 'fantasy',
      }
    ]
  }),
}

</script>
