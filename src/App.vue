<template>
  <div id="app">
    <div class="copyright">&copy; Copyright 2018 Private enterprise "Web Friends"<br /><a href="https://www.webfriends.by">www.webfriends.by</a></div>
    <Select/>
  </div>
</template>

<script>
import Select from './components/Select'

export default {
  name: 'App',
  components: {
    Select
  }
}
</script>

<style>
  .copyright {
    padding: 30px 0 20px 0;
    text-align: center;
    font-family: 'Avenir', Helvetica, Arial, sans-serif;
    font-size: 18px;
    opacity: 0.6;

    a {
      color: #02C8F3;

      &:visited {
        color: #02C8F3;
      }
    }
  }
</style>
