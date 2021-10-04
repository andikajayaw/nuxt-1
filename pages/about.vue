<template>
  <div class="container">
    <h3>Index home</h3>
    <ul>
      <li v-for="user,index in users" :key="index">
        {{user.name}}|
         {{user.name}}
      </li>
    </ul>
  </div>
</template>

<script>
export default {
  data(){
    return {
      users:[]
    }
  },
  async fetch(){
   const data=await this.$axios.$get('https://jsonplaceholder.typicode.com/users')
   this.users=data
  }
}
</script>
