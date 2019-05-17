<template>
  <div id="app">
    <div id="nav">
      <router-link to="/">Home</router-link> |
      <span class="router-button" @click="toPage('About')">About</span> |
      <span class="router-button" @click="toPage('A')">PageA</span> |
      <span class="router-button" @click="toPage('B')">PageB</span> |
    </div>
    <router-view/>
  </div>
</template>

<script>
export default {
  methods: {
    toPage(name) {
      if (name === 'About') {
        alert('spa模式');
      } else if (name === 'A') {
        this.$router.push({ name: 'pageA'})
      } else if (name === 'B') {
        this.$router.push({ name: 'pageB', params: { userId: 123 }})
      }
    }
  },
}
</script>

<style lang="stylus">
#app
  font-family 'Avenir', Helvetica, Arial, sans-serif
  -webkit-font-smoothing antialiased
  -moz-osx-font-smoothing grayscale
  text-align center
  color #2c3e50

#nav
  padding 30px
  a
    font-weight bold
    color #2c3e50
    &.router-link-exact-active
      color #42b983

.router-button
  font-weight: bold;
  color: #2c3e50;
  text-decoration: underline;
  cursor: pointer;

</style>
