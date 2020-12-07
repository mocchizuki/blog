<template>
  <main class="main">
    <h1 class="title">{{ title }}</h1>
    <p class="publishedAt">{{ publishedAt }}</p>
    <div class="post" v-html="body"></div>
  </main>
</template>

<script>
import axios from 'axios'

export default {
  async asyncData({ params }) {
    const { data } = await axios.get(
      `https://mczk.microcms.io/api/v1/blog/${params.slug}`,
      {
        headers: { 'X-API-KEY': 'd8d3d5dd-f732-48da-bb32-29ebf7de8220' }
      }
    )
    return data
  }
}
</script>