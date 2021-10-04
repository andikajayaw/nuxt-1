<template>
  <div class="container">
    <h3>Index home</h3>
    <ul>
      <li v-for="user,index in users" :key="index">
        {{user.name}}|
         <nuxt-link class="btn btn-primary btn-sm" :to="`/user/${user.id}`" >detail</nuxt-link>
      </li>
    </ul>
  </div>
</template>

<script>
export default {
  async asyncData({$axios}){
   const data=await $axios.$get('https://jsonplaceholder.typicode.com/users')
   return {users:data}
  }
}
</script>
