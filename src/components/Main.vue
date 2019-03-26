<template>
  <main>
    <Content1></Content1>
    <Content2></Content2>
  </main>
</template>

<script>
import Content1 from "./Content1";
import Content2 from "./Content2";

export default {
  name: "Main",
  components: {
    Content1,
    Content2
  }
};
</script>