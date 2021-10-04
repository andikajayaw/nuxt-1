<template>
  <div class="container">
    <pre>
            {{ user }}
        </pre
    >
  </div>
</template>

<script>
export default {
  async asyncData({ $axios, params }) {
    const data = await $axios.$get(
      `https://jsonplaceholder.typicode.com/users/${params.id}`
    )
    return { user: data }
  },
}
</script>

<style lang="scss" scoped></style>
