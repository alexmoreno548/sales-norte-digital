<template>
  <section>
    <ul class="nav d-flex align-items-start side__nav">
      <li class="nav-item">
        <a class="nav-link side__item-a" href="#">
          <img class="side__icon" src="@/assets/images/home.svg" alt>
        </a>
      </li>
      <li class="nav-item">
        <a class="nav-link side__item-a" href="#">
          <img class="side__icon" src="@/assets/images/star.svg" alt>
        </a>
      </li>
      <li class="nav-item">
        <a class="nav-link side__item-a" href="#">
          <img class="side__icon" src="@/assets/images/notification.svg" alt>
        </a>
      </li>
      <li class="nav-item">
        <a class="nav-link side__item-a" href="#">
          <img class="side__icon" src="@/assets/images/folder.svg" alt>
        </a>
      </li>
      <li class="nav-item">
        <a class="nav-link side__item-a" href="#">
          <img class="side__icon" src="@/assets/images/user.svg" alt>
        </a>
      </li>
    </ul>
  </section>
</template>

<script>
export default {
  name: "Sidebar"
};
</script>

<style lang="scss">
.side__nav {
  height: 100%;
  width: 5%;
  position: fixed;
  z-index: 1;
  top: 0;
  left: 0;
  background-color: #35a8f9;
  overflow-x: hidden;
  padding-top: 20px;
  padding-top: 52px;
  padding-bottom: 13%;
}
.side__item-a {
  margin-left: 10px;
}
.side__icon {
  width: 15px;
}
</style>