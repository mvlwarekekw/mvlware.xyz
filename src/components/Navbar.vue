<script setup lang="ts">

</script>

<template>
  <nav>
    <div class="navbar">
      <div class="nav-items">
        <ul>
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
      <a target="_blank" rel="noopener noreferrer" href="https://github.com/mvlwarekekw"><img src="/src/assets/github-light.svg" alt="" class="gh-logo"></a>
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

.nav-items {
  display: flex;
  width: 100%;
  justify-content: flex-end;
}

.nav-items ul {
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
}

</style>