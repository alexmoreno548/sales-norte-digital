<template>
  <header class="banner">
    <div class="container">
      <b-navbar toggleable="lg" type="dark">
        <b-navbar-brand></b-navbar-brand>

        <b-navbar-toggle target="nav_collapse" class="hero__toggle"/>

        <b-collapse is-nav id="nav_collapse">
          <!-- Right aligned nav items -->
          <b-navbar-nav class="ml-auto">
            <ul class="navbar-nav nav__item">
              <li class="nav-item">
                <a href>Content 1</a>
              </li>
              <li class="nav-item nav__item">
                <a href>Content 2</a>
              </li>
              <li class="nav-item">
                <router-link to="/sales/new">Login</router-link>
              </li>
            </ul>
          </b-navbar-nav>
        </b-collapse>
      </b-navbar>
    </div>
    <Hero></Hero>
  </header>
</template>

<script>
import Hero from "./Hero";

export default {
  name: "Header",
  components: {
    Hero
  }
};
</script>

<style lang="scss">
.header__navigation {
  font-size: 20px;
  margin-bottom: 40px;
  font-weight: 600;
}

.hero__toggle {
  background-color: #35a8f9;
}

.nav__item li {
  margin-left: 25px;
  margin-right: 25px;
  padding-top: 45px;
  padding-bottom: 20px;

  &:last-of-type {
    a {
      color: #35a8f9;
    }
  }

  a {
    text-decoration: none;
    color: black;
    font-weight: 500;
  }
}

.banner {
  min-height: 100vh;
  background-image: url("../assets/images/bg.svg");
  background-repeat: no-repeat;
  background-position-x: right;
  background-size: contain;
  display: flex;
  flex-direction: column;
}
</style>