<template lang="md">
## Hello markdown

**Current** route is:{{$route.path}}

```js
const a = 1;
```
</template>

<script>
export default {
  layout: "blog",
  created() {
    const routeStr = this.$nuxt.$route.path;
    const lastChar = routeStr.charAt(routeStr.length - 1);

    console.log(lastChar);
    if (lastChar === "/") {
      const newstr = routeStr.substr(0, routeStr.length - 1);
      // console.log(newstr);
      this.$router.go(newstr);
    }
  },
};
</script>

<style></style>
