<template>
  <section id="about" class="hight-5">
    <h1 class="about-title">
      {{ $t('about.title') }}
    </h1>
    <img :src="require(`~/assets/images/${$t('about.picture')}`)" width="300">
    <article>
      <p>&nbsp;&nbsp;{{ $t('about.about') }}</p>
      <br>
      <p>Skill: python, data science, javascript, React, Vue.js</p>
      <a :href="$t('about.resume_link')" target="_blank">{{ $t('about.resume') }}</a>
      <a v-if="$t('about.workHistory')" :href="$t('about.workHistory_link')" target="_blank">{{ $t('about.workHistory') }}</a>
    </article>
  </section>
</template>

<script>
export default {}
</script>

<style lang="scss" scoped>
img{
  margin: 30px;
  border-radius: 10px;
  box-shadow: 5px 5px #18181833
}
article{
  padding: 0 20px;
  line-height: 1.3;
}
$a_color:#18ac05d8;
a{
  font-size: 1.2rem;
  text-align: center;
  text-decoration: none;
  color: $a_color;
  border: solid 1px $a_color;
  border-radius: 5px;
  padding: 0.3rem;
  box-sizing: border-box;
  margin: 1rem 0;
  display: inline-block;
  background-size: 200% 100%;
  background-image: linear-gradient(to right, #FFFFFF 50%, $a_color 50%);
  transition: background-position 0.5s ease-in-out;

  &:hover{
  color: #FFFFFF;
  background-position: -100% 0;
  }
}
@media (max-width: 375px) {
  img {
    width: 80%;
  }
}
@media (min-width: 600px) {
  article {
    width: 500px;
  }
}
</style>
