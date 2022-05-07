<template>
  <div>
    <div class="diss">
      <img src="/1.jpg" alt="" />
    </div>
    <ul>
      <li><nuxt-link :to="{ name: 'index' }">HOME</nuxt-link></li>
      <li><nuxt-link :to="{ name: 'about' }">About</nuxt-link></li>
      <li>
        <nuxt-link :to="{ name: 'news', params: { newsId: 3306 } }">
          News
        </nuxt-link>
      </li>
      <li><nuxt-link :to="{ name: 'asyncData' }">asyncData</nuxt-link></li>
    </ul>
  </div>
</template>

<script>
export default {
  name: "IndexPage",
};
</script>

<style scoped>
.diss {
  width: 300px;
  height: 100px;
  background-image: url("~static/v.png");
}
</style>
