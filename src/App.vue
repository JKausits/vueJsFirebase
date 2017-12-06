<template>
  <div id="app">
    
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

let bookRef = db.ref('books');
export default {
  name: 'app',
  firebase: {
    books: booksRef
  },
  components: {
  }
}
</script>

<style>
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
