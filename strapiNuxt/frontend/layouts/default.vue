<template>
  <div id="app-container">
    <Header />
    <div class="app-container">
      <Nuxt />
    </div>
    <Footer />
  </div>
</template>

<style scoped lang="scss">
@import '~/assets/styles/variables.scss';
@import '~/assets/styles/style.scss';
</style>

<script>
export default {
    name: "DefaultLayout",
    data() {
        return {};
    },
}
</script>
