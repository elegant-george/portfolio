<template>
  <Nuxt />
</template>

<script>
export default {}
</script>

<style lang="scss">
*, *:before, *:after {
  padding: 0;
  margin: 0;
  box-sizing: border-box;
}
html, body {
  background-color: #fff;
  color: #2e2f30;
  letter-spacing: 0.5px;
  font-size: 18px;
  font-family: "Source Sans Pro", Arial, sans-serif;
  height: 100vh;
  margin: 0;
  background-image: url('~assets/images/pexels-pixabay-373076.jpg');
  background-size: cover;
  background-repeat: no-repeat;
  background-attachment: fixed;
}
section{
  min-height: 100vh;
  position: relative;
  width: 80%;
  margin: 0 auto;
}
h1{
  font-size: 2rem;
  font-weight: 700;
  line-height: 1.3;
}
.hight-20{
  padding-top: calc(20vh + 80px);
}
.hight-5{
  padding-top: calc(5vh + 80px);
}
</style>
