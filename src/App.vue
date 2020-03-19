<template>
    <div id="app">
        <div>
            <b-navbar class="navbar" id="nav" toggleable="lg" fixed="top">
                <b-navbar-brand  class="navbar-brand" href="#home">
                    <img src="./assets/images/logo.png" alt="logo" class="logo">
                </b-navbar-brand>

                <b-navbar-toggle target="nav-collapse"></b-navbar-toggle>

                <b-collapse id="nav-collapse" class="nav-collapse" is-nav>
                    <b-navbar-nav class="ml-auto">
                        <b-nav-item class="nav-item" href="#home" right>Home</b-nav-item>
                        <b-nav-item class="nav-item" href="#profile" right>Profile</b-nav-item>
                        <b-nav-item class="nav-item" href="#services" right>Services</b-nav-item>
                        <b-nav-item class="nav-item" href="#education" right>Education</b-nav-item>
                        <b-nav-item class="nav-item" href="#experiences" right>Experiences
                        </b-nav-item>
                        <b-nav-item class="nav-item" href="#portfolio" right>Portfolio</b-nav-item>
                        <b-nav-item class="nav-item" href="#contact" right>Contact</b-nav-item>
                    </b-navbar-nav>
                </b-collapse>
            </b-navbar>
        </div>
        <router-view />
    </div>
</template>

<script>
export default {
  mounted() {
    this.$nextTick(() => {
      window.addEventListener('scroll', () => {
        const navbar = document.getElementById('nav');
        // eslint-disable-next-line camelcase
        const nav_class = navbar.classList;
        if (document.documentElement.scrollTop >= 150) {
          if (nav_class.contains('shrink') === false) {
            nav_class.toggle('shrink');
          }
        } else if (nav_class.contains('shrink') === true) {
          nav_class.toggle('shrink');
        }
      });
    });
  },
};
</script>

<style>
@import 'css/style.css';
</style>
