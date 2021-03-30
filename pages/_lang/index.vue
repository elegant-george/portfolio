<template>
  <div>
    <Header />
    <Introduction />
    <About />
    <Projects />
    <Contact />
    <Footer />
  </div>
</template>

<script>
export default {
  head () {
    return { title: this.$t('page-title') }
  }
}
</script>
