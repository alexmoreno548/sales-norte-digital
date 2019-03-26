<template>
  <section class="content2">
    <div class="container">
      <div class="row content2__wrapper-cloud-title">
        <div class="col-md-8 content2__wrapper-cloud"></div>
        <div class="col-md-4 col-12 content2__wrapper-title-content">
          <h2 class="content2__title">Content 2</h2>
          <p class="content2__content">
            Lorem ipsum dolor sit amet, consectetur adipi-
            scing elit, sed do eiusmod tempor incididunt ut
            labore et dolore magna aliqua
          </p>
        </div>
      </div>
      <div class="row">
        <div class="col-md-4">
          <img src="@/assets/images/page-blue.svg" alt>
        </div>
        <div class="col-md-4">
          <img src="@/assets/images/page-white.svg" alt>
        </div>
        <div class="col-md-4">
          <img src="@/assets/images/page-blue.svg" alt>
        </div>
      </div>
    </div>
  </section>
</template>

<script>
export default {
  name: "Content2"
};
</script>

<style lang="scss">
.content2__title {
  font-weight: bold;
  font-size: 45px;
  text-align: right;
}

.content2__content {
  text-align: right;
  color: $subtitle-color;
}

.content2 {
  background-color: #edf5fe;
  padding-bottom: 50px;
}

.content2__wrapper-title-content {
  margin-top: 115px;
}

.content2__wrapper-cloud {
  background-image: url("../assets/images/clouds.svg");
  background-repeat: no-repeat;
  background-position-y: 95px;
  background-position-x: 105px;
  background-size: 70%;
}

.content2__wrapper-cloud-title {
  margin-bottom: 30px;
}
</style>