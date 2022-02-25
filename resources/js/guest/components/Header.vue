<template>
  <header>
    <h2>------------------- Header ----------------------</h2>
    <a href="/admin/home">Area riservata</a>
    <nav>
      <ul>
        <li>
          <router-link :to="{ name: 'home' }">Home</router-link>
        </li>
        <li>
          <router-link :to="{ name: 'about' }">Chi siamo</router-link>
        </li>
        <li>
          <router-link :to="{ name: 'categories' }">Categorie</router-link>
        </li>
      </ul>
    </nav>
  </header>
</template>

<script>
export default {
  name: "Header",
};
</script>

<style>
</style>