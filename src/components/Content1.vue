<template>
  <section id="content1">
    <div class="container">
      <div class="row">
        <div class="col-md-6 col-12">
          <h2 class="content1__title">Content 1</h2>
          <p class="content1__sub-title">
            Lorem ipsum dolor sit amet, consectetur adipi-
            scing elit, sed do eiusmod tempor incididunt ut
            labore et dolore magna aliqua
          </p>
        </div>
      </div>
      <div class="row">
        <div class="col-md-3">
          <img src="@/assets/images/card-img.svg" alt>
          <p
            class="content1__card-content"
          >Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua</p>
        </div>
        <div class="col-md-3">
          <img src="@/assets/images/card-img.svg" alt>

          <p
            class="content1__card-content"
          >Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua</p>
        </div>
        <div class="col-md-3">
          <img src="@/assets/images/card-img.svg" alt>

          <p
            class="content1__card-content"
          >Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua</p>
        </div>
        <div class="col-md-3">
          <img src="@/assets/images/card-img.svg" alt>
          <p
            class="content1__card-content"
          >Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua</p>
        </div>
      </div>
    </div>
  </section>
</template>

<script>
export default {
  name: "Content1"
};
</script>

<style lang="scss">
.content1__title {
  font-weight: bold;
  font-size: 45px;
  text-align: left;
}

.content1__sub-title {
  text-align: left;
  color: $subtitle-color;
}

.content1__card-content {
  margin-top: 15px;
  font-size: 14px;
  color: $subtitle-color;
  text-align: left;
}

#content1 {
  margin-bottom: 65px;
}
</style>
