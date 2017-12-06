<template>
  <div id="app" class="container">
    <div class="page-header">
      <h1>Vue.js 2 & Firebase Sample Application</h1>
    </div>

    <div class="panel panel-default">
      <div class="panel-heading">
        <h3>Books List</h3>
      </div>
      <div class="panel-body">
        <table class="table table-striped">
          <thead>
            <tr>
              <th>
                Title
              </th>
              <th>
                Author
              </th>
            </tr>
          </thead>
          <tbody>
            <tr v-for="book in books" v-bind:key="book.id">
              <td>
                <a v-bind:href="book.url">{{book.title}}</a>
              </td>
              <td>
                {{book.author}}
              </td>
            </tr>
          </tbody>
        </table>
      </div>
    </div>
  </div>
</template>

<script>

import Firebase from 'firebase'

let config = {
  apiKey: "AIzaSyA8elobDTbF77ZxbVKJNL2RB-sqHcUvxQA",
  authDomain: "vuejs-firebase-01-a8ee4.firebaseapp.com",
  databaseURL: "https://vuejs-firebase-01-a8ee4.firebaseio.com",
  projectId: "vuejs-firebase-01-a8ee4",
  storageBucket: "vuejs-firebase-01-a8ee4.appspot.com",
  messagingSenderId: "241673180100"
}

let app = Firebase.initializeApp(config);
let db = app.database();

let booksRef = db.ref('Books');
export default {
  name: 'app',
  firebase: {
    books: booksRef
  },
  components: {
  },
  data(){
    return{
      newBook: {
        title: '',
        author: '',
        url: ''
      }
    }
  }
}
</script>

<style>

</style>
