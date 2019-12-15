<template>
  <div id="">
    <h1>Other</h1>
    <!-- <p>{{ users[0].id }}</p>
    <p>{{ users[0].names }}</p> -->
    <ul>
      <li v-for="user in users" v-bind:key="user.id">
        {{ user.id }}: {{ user.name }} - {{ user.company.name }}
      </li>
    </ul>

  </div>
</template>
<script>

const axios =  require('axios')
let url = 'https://jsonplaceholder.typicode.com/users'

export default {
asyncData({ params }){
  return axios.get(url)
    .then((res) => {
      return { users: res.data }
    })
  }
}
</script>
<style lang="scss" scoped>
</style>
