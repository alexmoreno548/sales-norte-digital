<template>
  <section>
    <Header></Header>
    <Main></Main>
    <Footer></Footer>
  </section>
</template>

<script>
// @ is an alias to /src
import Header from "@/components/Header";
import Main from "@/components/Main";
import Footer from "@/components/Footer";

export default {
  name: "home",
  components: {
    Header,
    Main,
    Footer
  }
};
</script>
