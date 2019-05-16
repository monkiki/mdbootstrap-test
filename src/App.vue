<template>
  <div id="app">
    <div id="nav">
      <router-link to="/">Home</router-link> |
      <router-link to="/about">About</router-link>
    </div>
    <router-view/>
    <mdb-alert color="primary">Hello, I'm an alert!</mdb-alert>
    <mdb-btn @click.native="modal = true">Hello world</mdb-btn>
    <mdb-modal :show="modal" @close="modal = false">
      <mdb-modal-header>
        <mdb-modal-title>Modal title</mdb-modal-title>
      </mdb-modal-header>
      <mdb-modal-body>...</mdb-modal-body>
      <mdb-modal-footer>
        <mdb-btn color="secondary" @click.native="modal = false">Close</mdb-btn>
        <mdb-btn color="primary">Save changes</mdb-btn>
      </mdb-modal-footer>
    </mdb-modal>
  </div>
</template>

<script>
  import {mdbBtn, mdbAlert, mdbModal, mdbModalHeader, mdbModalTitle, mdbModalBody, mdbModalFooter} from 'mdbvue';

  export default {
    components: {
      mdbBtn, mdbAlert, mdbModal, mdbModalHeader, mdbModalTitle, mdbModalBody, mdbModalFooter
    },
    data() {
      return {
        modal: false
      };
    },
    methods: {
      success() {
        // This is an MDB Pro Component
        this.$notify.success({message: 'Hi! I am success message.', position:'top right', timeOut: 5000});
      }
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
  }
  #nav {
    padding: 30px;
  }

  #nav a {
    font-weight: bold;
    color: #2c3e50;
  }

  #nav a.router-link-exact-active {
    color: #42b983;
  }
</style>
