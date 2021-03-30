<template>
  <footer>
    <nav class="external_links">
      <a href="https://github.com/elegant-george" target="_blank">
        <font-awesome-icon :icon="['fab', 'github', ]" size="2x" />
      </a>
      <a href="https://www.linkedin.com/in/%E8%82%B2%E4%BB%BB-%E6%9E%97-1ab60915b/" target="_blank">
        <font-awesome-icon :icon="['fab', 'linkedin-in', ]" size="2x" />
      </a>
    </nav>
    <nav class="change_langs">
      <NuxtLink :to="`/`" class="lang" active-class="active" exact>English</NuxtLink>
      <NuxtLink :to="`/jp`" class="lang" active-class="active" exact>日本語</NuxtLink>
      <NuxtLink :to="`/ch`" class="lang" active-class="active" exact>中文</NuxtLink>
    </nav>
  </footer>
</template>

<script>
export default {}
</script>

<style lang="scss" scoped>
footer{
  background-color: #f39315b0;
  padding: 1rem;
  text-align: center;
}
.external_links{
  a{
    color: #FFFFFF;
    margin: 0 10px;
  }
}
.change_langs{
  margin-top: 15px;
  a{
    text-decoration: none;
    color: #FFFFFF;
    border: 1px solid #FFFFFF;
    padding: 5px;
    border-radius: 5px;
    text-align: center;
    margin: 0 5px;
  }
  .active {
    background-color: #FFFFFF;
    color: #f39315b0;
  }
}
</style>
