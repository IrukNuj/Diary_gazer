<template>
  <section>
    <div>
      <ul>
        <li v-for="item in items" :key="item">
          <h1>- <a :href="item.html_url">{{ item.title }}</a></h1>
        </li>
      </ul>
    </div>
  </section>
</template>

<script>
export default {
  async asyncData({ route, app }) {
    const items = await app.$axios.$get(`https://api.github.com/repos/${route.params.userName}/${route.params.repository}/pulls`)
    return { items }
  }
}
</script>
