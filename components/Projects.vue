<template>
  <section id="projects" class="hight-5">
    <h1>{{ $t('projects.title') }}</h1>
    <div class="projects_container">
      <article v-for="project in $t('projects.projects')" :key="project.title" class="project">
        <h2>{{ project.title }}</h2>
        <img :src="require(`~/assets/images/${project.thumbnail}`)" width="200">
        <p>&nbsp;&nbsp;{{ project.about }}</p>
        <nav>
          <a v-if="project.demo" :href="project.demo" target="_blank" class="demo">demo</a>
          <a v-if="project.source_code" :href="project.source_code" target="_blank" class="code">code</a>
        </nav>
      </article>
    </div>
  </section>
</template>

<script>
export default {}
</script>

<style lang="scss" scoped>
.projects_container{
  display: flex;
  flex-wrap: wrap;
}
.project{
  margin: 20px;
  width: 200px;
  p{
    padding: 0 10px;
    line-height: 1.3;
  }
  nav{
    margin: 1.5rem auto;
    position: relative;
    .demo{
      position: absolute;
      left: 25%;
      transform: translate(-50%, -50%);
    }
    .code{
      position: absolute;
      left: 75%;
      transform: translate(-50%, -50%);
    }
    a{
      text-decoration: none;
      color: #092effd8;
      border: solid 1px #092effd8;
      border-radius: 5px;
      padding: 0.3rem;
      box-sizing: border-box;
      background-size: 200% 100%;
      background-image: linear-gradient(to right, #FFFFFF 50%, #092effd8 50%);
      transition: background-position 0.5s ease-in-out;

      &:hover{
      color: #FFFFFF;
      background-position: -100% 0;
      }
    }
  }
}
@media (max-width: 300px) {
  img {
    width: 100%;
  }
}
</style>
