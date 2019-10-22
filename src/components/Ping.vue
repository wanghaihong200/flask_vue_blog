<template lang="html">
  <div>
    <p>{{ msg }}</p>
  </div>
</template>

<script>
import axios from 'axios'

export default {
  name: 'Ping',
  data () {
    return {
      msg: 'Hello, this is Ping.vue component'
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
  },
  created () {
    this.getMessage()
  }
}
</script>

<style lang="css" scoped>

</style>
