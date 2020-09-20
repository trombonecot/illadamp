<template>
  <div class="container">
    <img class="mapa" src="https://camo.githubusercontent.com/b314dff28b836db80966fece1c49896d6e8788ef/68747470733a2f2f696e6b61726e6174652d6170692d61732d70726f64756374696f6e2e73332e616d617a6f6e6177732e636f6d2f6d3935336568776d363570387061746f34666b737968776e39336530" />
  </div>
</template>

<script>
  export default {
    async asyncData({ $content, params }) {
      const articles = await $content('articles', params.slug)
        .only(['title', 'description', 'img', 'slug', 'author'])
        .sortBy('createdAt', 'asc')
        .fetch()

      return {
        articles
      }
    }
  }
</script>

<style>
body {
  background: lightgrey;
}
.container {
  margin: 0 auto;
  min-height: 100vh;
  display: flex;
  justify-content: center;
  align-items: center;
  text-align: center;
  width: 100%;
}

.mapa {
  margin: 50px auto;
  width: 1200px;
  display: block;
}

.title {
  font-family:
    'Quicksand',
    'Source Sans Pro',
    -apple-system,
    BlinkMacSystemFont,
    'Segoe UI',
    Roboto,
    'Helvetica Neue',
    Arial,
    sans-serif;
  display: block;
  font-weight: 300;
  font-size: 100px;
  color: #35495e;
  letter-spacing: 1px;
}

.subtitle {
  font-weight: 300;
  font-size: 42px;
  color: #526488;
  word-spacing: 5px;
  padding-bottom: 15px;
}

.links {
  padding-top: 15px;
}
</style>
