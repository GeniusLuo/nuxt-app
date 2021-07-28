<template>
  <div class="container">
    <div>
      <logo />
      <p>邮箱：<input v-model="username" type="text" /></p>
      <p>密码：<input v-model="password" type="text" /></p>
      <p>验证码：<input v-model="code" type="text" /></p>
      <p>sid：<input v-model="sid" type="text" /></p>
      <p><button type="button" @click="login">登录</button></p>
    </div>
  </div>
</template>

<script>
import Logo from '~/components/Logo.vue'

export default {
  name: 'Index',
  components: {
    Logo
  },
  data() {
    return {
      username: '',
      password: '',
      code: '',
      sid: ''
    }
  },
  mounted() {
    window.vue = this
  },
  methods: {
    login() {
      this.$auth.loginWith('local', {
        data: {
          username: this.username,
          password: this.password,
          code: this.code,
          sid: this.sid
        }
      })
    }
  }
  // async asyncData({ $axios }) {
  //   const result = await $axios.$get('http://localhost:4000/posts')
  //   return {
  //     posts: result
  //   }
  // }
}
</script>

<style>
.container {
  margin: 0 auto;
  min-height: 100vh;
  display: flex;
  justify-content: center;
  align-items: center;
  text-align: center;
}

.title {
  font-family: 'Quicksand', 'Source Sans Pro', -apple-system, BlinkMacSystemFont,
    'Segoe UI', Roboto, 'Helvetica Neue', Arial, sans-serif;
  display: block;
  font-weight: 300;
  font-size: 100px;
  color: #35495e;
  letter-spacing: 1px;
}

.subtitle {
  font-weight: 300;
  font-size: 42px;
  color: #526488;
  word-spacing: 5px;
  padding-bottom: 15px;
}

.links {
  padding-top: 15px;
}
</style>
