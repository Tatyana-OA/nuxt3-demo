<template>
  <nav>
    <NuxtLink to="/">Home</NuxtLink>
  </nav>
  <main>
    <!-- Outlet for content -->
    <slot />
  </main>
</template>

<style scoped>
nav {
  background-color: #f5f5f5;
  padding: 10px 20px;
  border-bottom: 1px solid #ddd;
  text-align: center;
}

nav a {
  color: #333;
  text-decoration: none;
  font-size: 2rem;
}

nav a:hover {
  color: #555;
}

main {
  padding: 20px;
  margin: 20px auto;
  max-width: 800px;
  font-family: Arial, sans-serif;
}
</style>
