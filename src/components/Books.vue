<template>
  <v-card>
    <v-card-title>
      <v-btn color="primary">add to cart</v-btn>
      <v-spacer></v-spacer>
      <v-text-field
          v-model="search"
          append-icon="mdi-magnify"
          label="Search"
          single-line
          hide-details
      ></v-text-field>
    </v-card-title>
    <v-data-table
        v-model="selected"
        :headers="headers"
        :items="books"
        :search="search"
        :single-select="singleSelect"
        item-key="name"
        show-select
    ></v-data-table>
  </v-card>
</template>

<script>
export default {
  name: 'books',
  data: () => ({
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
  })
}
</script>

<style scoped>

</style>