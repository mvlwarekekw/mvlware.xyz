<script setup lang="ts">
import { ref } from "vue";

const burger = ref(true)
const menu = ref(false)

function toggle() {
  burger.value = !burger.value
  menu.value = !menu.value
}
</script>

<template>
  <nav>
    <div class="navbar">
      <div class="nav-menu" :class="{'active' : burger}">
        <ul class="nav-items" :class="{'active': burger}">
          <li class="nav-item">
            <RouterLink to="/" class="link">Home</RouterLink>
          </li>
          <li class="nav-item">
            <RouterLink to="/about" class="link">About</RouterLink>
          </li>
          <li class="nav-item">
            <RouterLink to="/projects" class="link">Projects</RouterLink>
          </li>
        </ul>
      </div>
      <a target="_blank" rel="noopener noreferrer" href="https://github.com/mvlwarekekw"><img src="/github-light.svg" alt="" class="gh-logo"></a>
      <div class="burger" :class="{'active' : burger}" @click="toggle">
        <span class="bar"></span>
        <span class="bar"></span>
        <span class="bar"></span>
      </div>
    </div>
  </nav>
</template>

<style scoped>

.link {
  text-decoration: none;
  color: #fff;
}

.navbar {
  margin: 15px 0;
  padding-right: 40px;
  display: flex;
  flex-direction: row;
  align-items: center;
  max-height: 100px;
}

.burger {
  display: none;
}

.bar {
  display: block;
  width: 30px;
  height: 3px;
  margin: 5px auto;
  transition: all 0.3s ease-in-out;
  background-color: #fff;
}

@media screen and (max-width: 768px) {
  .nav-menu {
    position: fixed;
    left: -100%;
    top: 6rem;
    width: 100vw;
    height: 100vh;

    background-color: #131313;
    border-radius: 15px;
    text-align: center;
    transition: 0.3s;
  }

  .nav-items {
    position: fixed;
    left: -100%;

    display: flex;
    flex-direction: column !important;

    align-items: center;
    justify-content: center;

    width: 77%;
    height: 60%;
  }

  .nav-items li {
    margin: 2rem 0;
    font-size: 2rem;
  }

  .nav-menu.active, .nav-items.active {
    left: 0;
  }

  .burger {
    display: block;
    cursor: pointer;
    position: absolute;
    right: 50px;
  }

  .gh-logo {
    position: relative;
    left: 8%;
    top: 6px;
  }

  .burger.active .bar:nth-child(2) {
    opacity: 0;
  }

  .burger.active .bar:nth-child(1) {
    transform: translateY(8px) rotate(45deg);
  }

  .burger.active .bar:nth-child(3) {
    transform: translateY(-8px) rotate(-45deg);
  }

}

.nav-menu {
  display: flex;
  width: 100%;
  justify-content: flex-end;
}

.nav-menu ul {
  display: flex;
  flex-direction: row;
}

.nav-item {
  margin: 0 40px;
  font-size: 1.3rem;
}

.gh-logo {
  width: 40px;
  margin: 0 25px;
  padding-top: 5px;
}

</style>