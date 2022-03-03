<template>
  <div>
    <h2>News Index page</h2>
    <p>NewsID:{{ $route.params.newsId }}</p>
    <ul>
      <li><nuxt-link :to="{ name: 'index' }">Home</nuxt-link></li>
      <!-- <li><nuxt-link :to="{ name: 'news/123' }">new-1</nuxt-link></li>
      <li><nuxt-link :to="{ name: 'news/456' }">new-2</nuxt-link></li> -->
      <li><a href="/news/123">new-1</a></li>
      <li><a href="/news/4a6">new-2</a></li>
    </ul>
  </div>
</template>
