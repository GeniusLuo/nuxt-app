<template>
  <div class="nav-bar">
    <nuxt-link class="link" to="/create">create link</nuxt-link>
    <nuxt-link class="link" to="/list">list link</nuxt-link>
    <nuxt-link class="link" to="/about">about link</nuxt-link>
  </div>
</template>

<script>
export default {
  name: 'Navbar',
  components: {},
  data() {
    return {}
  },
  mounted() {},
  methods: {}
}
</script>

<style lang="scss" scoped>
.nav-bar {
  .link {
    margin-right: 10px;
  }
}
</style>
