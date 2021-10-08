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
  head: {
      // @src https://nuxtjs.org/docs/features/meta-tags-seo/
    title: 'my website title',
    meta: [
      { charset: 'utf-8' },
      { name: 'viewport', content: 'width=device-width, initial-scale=1' },
      {
        hid: 'description',
        name: 'description',
        content: 'my website description'
      }
    ],

  }
}
</script>

<style lang="scss" scoped></style>
