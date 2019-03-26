<template>
  <div class="container hero__container">
    <div class="row align-items-center">
      <div class="col-md-5 hero__wrapper-content">
        <h1 class="hero__title">Lorem ipsum Design</h1>
        <p class="hero__sub-title">
          Lorem ipsum dolor sit amet, consectetur adipi-
          scing elit, sed do eiusmod tempor incididunt ut
          labore et dolore magna aliqua
        </p>
        <button class="hero__btn btn-primary">LOGIN</button>
      </div>
      <div class="col-md-7">
        <img src="@/assets/images/pc.svg" alt>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: "Hero"
};
</script>

<style lang="scss">
.hero__title {
  font-weight: bold;
  font-size: 55px;
}

.hero__sub-title {
  color: #999999;
}

.hero__btn {
  background-color: transparent;
  border: 1px solid transparent;
  font-weight: bold;
  font-size: 20px;
  border-radius: 0px;
  padding-top: 10px;
  padding-bottom: 10px;
  padding-left: 30px;
  padding-right: 30px;
  margin-top: 70px;
}

.hero__container {
  min-height: 70vh;
  display: flex;
  align-items: center;
}

.hero__wrapper-content {
  text-align: left;
}
</style>