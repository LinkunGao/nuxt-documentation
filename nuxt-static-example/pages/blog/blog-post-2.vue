<template>
  <div>
    <button @click="goHome">hhh</button>
  </div>
</template>

<script>
export default {
  methods: {
    goHome() {
      console.log(this.$nuxt.$route.path);
      this.$router.push({ name: "video" });
    },
  },
};
</script>

<style></style>
