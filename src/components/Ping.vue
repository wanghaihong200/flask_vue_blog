<template>
  <div class="container">
    <button class="btn btn-primary" type="button" @click="getMessage">
      {{ msg }}
    </button>
  </div>
</template>

<script>
import axios from 'axios'

export default {
  name: 'Ping',
  data () {
    return {
      msg: '前后端通信测试'
    }
  },
  methods: {
    getMessage () {
      const path = 'http://127.0.0.1:8000/api/ping'
      axios.get(path)
        .then((res) => {
          this.msg = res.data
        })
        .catch((error) => {
          console.error(error)
        })
    }
  }
}
</script>

<style lang="css" scoped>

</style>
