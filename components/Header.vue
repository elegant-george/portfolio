<template>
  <header>
    <nav class="navbar" :class="{ 'navbar--hidden': !showNavbar }">
      <a v-scroll-to="{el: '#intro', duration: 800}" class="nava intro active" href="#intro">
        Top
      </a>
      <a v-scroll-to="{el: '#about', duration: 800}" class="nava about" href="#about">
        About
      </a>
      <a v-scroll-to="{el: '#projects', duration: 800}" class="nava projects" href="#projects">
        My Works
      </a>
      <a v-scroll-to="{el: '#contact', duration: 800}" class="nava contact" href="#contact">
        Contact
      </a>
    </nav>
  </header>
</template>

<script>
export default {
  data () {
    return {
      sections: null,
      nava: null,
      showNavbar: false,
      lastScrollPosition: 0
    }
  },
  mounted () {
    this.sections = document.querySelectorAll('section')
    this.nava = document.querySelectorAll('.nava')
    window.addEventListener('scroll', this.onScroll)
  },
  beforeDestroy () {
    window.removeEventListener('scroll', this.onScroll)
  },
  methods: {
    onScroll () {
      let current = ''
      this.sections.forEach((section) => {
        const sectionTop = section.offsetTop
        const sectionHeight = section.clientHeight
        if (pageYOffset >= sectionTop - sectionHeight / 5) {
          current = section.getAttribute('id')
        }
      })
      this.nava.forEach((a) => {
        a.classList.remove('active')
        if (a.classList.contains(current)) {
          a.classList.add('active')
        }
      })
      // Get the current scroll position
      const currentScrollPosition = window.pageYOffset || document.documentElement.scrollTop
      // Because of momentum scrolling on mobiles, we shouldn't continue if it is less than zero
      if (currentScrollPosition < 0) {
        return
      }
      if (Math.abs(currentScrollPosition - this.lastScrollPosition) < 60) {
        return
      }
      // Here we determine whether we need to show or hide the navbar
      this.showNavbar = currentScrollPosition < this.lastScrollPosition && currentScrollPosition >= 60
      // Set the current scroll position as the last scroll position
      this.lastScrollPosition = currentScrollPosition
    }
  }
}
</script>

<style scoped lang="scss">
.navbar {
  width: 100%;
  padding: 5px;
  background: #f39315b0;
  position: fixed;
  z-index: 100;
  box-shadow: 0 1px 10px #f393158c;
  transform: translate3d(0, 0, 0);
  transition: 0.3s all ease-out;
  display: inline-flex;
  align-items: flex-end;
  justify-content: flex-end;
  flex-wrap: wrap;
}
.navbar.navbar--hidden {
  box-shadow: none;
  transform: translate3d(0, -100%, 0);
}
a{
  text-decoration: none;
  margin: 10px;
  color: white;
}
.active{
  border-bottom: solid #FFFFFF 2px;
  transition: 0.3s all ease-out;
}
</style>
