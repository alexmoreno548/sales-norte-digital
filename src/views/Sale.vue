<template>
  <section>
    <Sidebar></Sidebar>
    <MainSale></MainSale>
  </section>
</template>

<script>
import MainSale from "@/components/MainSale";
import Sidebar from "@/components/Sidebar";

export default {
  name: "Sale",
  components: {
    MainSale,
    Sidebar
  }
};
</script>

<style lang="scss">
</style>