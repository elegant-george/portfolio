<template>
  <section id="intro" class="hight-20">
    <h1 class="intro-title">
      {{ $t('intro.hello') }} <span class="name-highlight">{{ $t('intro.name') }}</span>{{ $t('intro.afterName')}}
      <br>
      {{ $t('intro.IamWhat') }}
    </h1>
    <a v-scroll-to="{el: '#about', duration: 800}" href="#about">
      Know more
    </a>
  </section>
</template>

<script>
export default {}
</script>

<style lang="scss" scoped>
.intro-title{
  animation: fadein 2s;
}
.name-highlight{
  color: #f39315;
}
$a_color:#18ac05d8;
a{
  width: 8rem;
  font-size: 1.2rem;
  text-align: center;
  text-decoration: none;
  color: $a_color;
  border: solid 1px $a_color;
  border-radius: 5px;
  padding: 0.3rem;
  box-sizing: border-box;
  margin: 0.5rem 0;
  display: inline-block;
  background-size: 200% 100%;
  background-image: linear-gradient(to right, #FFFFFF 50%, $a_color 50%);
  transition: background-position 0.5s ease-in-out;
  opacity: 0;
  animation: fadein 2s;
  animation-delay: 0.5s;
  animation-fill-mode: forwards;

  &:hover{
  color: #FFFFFF;
  background-position: -100% 0;
  }
}
@keyframes fadein {
  from { opacity: 0; }
  to   { opacity: 1; }
}
</style>
