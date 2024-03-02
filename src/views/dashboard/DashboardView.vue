<template>
  <h1>這是後台</h1>
  <nav>
    <RouterLink to="/admin/products">products</RouterLink> |
    <RouterLink to="/admin/cart">cart</RouterLink> |
    <RouterLink to="/">home</RouterLink> |
  </nav>
  <router-view></router-view>
</template>

<script>
import axios from 'axios'
const { VITE_URL } = import.meta.env

export default {
  methods: {
    checkAdmin () {
      const url = `${VITE_URL}/v2/api/user/check`
      axios.post(url)
        .then((res) => {
          console.log(res.data.success)
        })
        .catch(() => {
          console.log('error')
          this.$router.push('/login')
        })
    }
  },
  mounted () {
    // 取出 Token
    const token = document.cookie.replace(/(?:(?:^|.*;\s*)hexToken\s*=\s*([^;]*).*$)|^.*$/, '$1')
    axios.defaults.headers.common.Authorization = token

    this.checkAdmin()
  }
}
</script>
