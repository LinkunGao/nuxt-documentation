<template>
  <div>
    <h1>name: {{ info.name }}</h1>
    <h1>age: {{ info.age }}</h1>
  </div>
</template>

<script>
import axios from "axios";
export default {
  data() {
    return {
      name: "skycoco",
    };
  },
  //   asyncData() {
  //     return axios.get("http://myjson.dit.upm.es/api/bins/4m37").then((res) => {
  //       return { info: res.data };
  //     });
  //   },
  async asyncData() {
    let { data } = await axios.get("http://myjson.dit.upm.es/api/bins/4m37");
    return { info: data };
  },
};
</script>
