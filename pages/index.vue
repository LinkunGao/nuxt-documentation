<template>
  <div>
    <ul>
      <li><nuxt-link :to="{ name: 'index' }">HOME</nuxt-link></li>
      <li><nuxt-link :to="{ name: 'about' }">About</nuxt-link></li>
      <li>
        <nuxt-link :to="{ name: 'news', params: { newsId: 3306 } }">
          News
        </nuxt-link>
      </li>
    </ul>
  </div>
</template>

<script>
export default {
  name: "IndexPage",
};
</script>
