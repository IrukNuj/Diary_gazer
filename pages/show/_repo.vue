<template>
  <h1>{{ items }}</h1>
</template>

<script>

export default {
  async asyncData(app) {
    const items = await app.$axios.$get('https://api.github.com/repos/IrukNuj/mint_app')
    return { items }
  }
}
</script>
