<script setup lang="ts">

</script>

<template>
  <nav>
    <div class="navbar">
      <div class="nav-items">
        <ul>
          <li class="nav-item">Home</li>
          <li class="nav-item">About</li>
          <li class="nav-item">Projects</li>
        </ul>
      </div>
      <img src="/src/assets/github-light.svg" alt="" class="gh-logo">
    </div>
  </nav>
</template>

<style scoped>

.navbar {
  margin: 15px 0;
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
  font-size: 1.2rem;
}

.gh-logo {
  width: 40px;
  margin: 0 20px;
}

</style>