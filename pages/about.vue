<template>
  <div class="container">
    <h3>Index home</h3>
    <button class="btn btn-primary" @click.prevent="$fetch"> refresh</button>
    <ul v-if="!$fetchState.pending">
      <li v-for="user,index in users" :key="index">
        {{user.name}}|
         {{user.username}}
      </li>
    </ul>
    <span v-else>
      loading
    </span>
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
