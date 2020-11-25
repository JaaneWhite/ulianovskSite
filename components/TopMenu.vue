<template>
  <b-navbar toggleable="lg" class="top-menu-block">
    <b-navbar-toggle target="nav-collapse" class="burger-button"></b-navbar-toggle>
    <b-collapse id="nav-collapse" is-nav >
      <b-navbar-nav fill class="top-menu">
        <b-nav-item href="#" class="top-menu-item">Путеводители</b-nav-item>
        <b-nav-item href="#" class="top-menu-item">Указатели</b-nav-item>
        <b-nav-item href="#" class="top-menu-item">Муниципальные архивы <br>
          Ульяновской области</b-nav-item>
        <b-nav-item href="#" class="top-menu-item">Тематические базы данных</b-nav-item>
        <b-nav-item href="#" class="top-menu-item">Услуги</b-nav-item>
        <b-nav-item href="#" class="top-menu-item">Об архиве</b-nav-item>
        <b-nav-item href="#" class="top-menu-item">Контакты</b-nav-item>
      </b-navbar-nav>
    </b-collapse>

  </b-navbar>
</template>

<script>
export default {
  name: "TopMenu"
}
</script>

<style lang="scss" scoped>
  .top-menu-block {
    width: 100%;
    padding-right: 0;
    padding-left: 0;

    .top-menu {
      width: 100%;
      height: 50px;
      .top-menu-item {
        height: 100%;
        a {
          font-size: 15px;
          color: #474334;
          height: 100%;
          display: flex;
          align-items: center;

          &:hover {
            font-size: 15px;
            color: #474334;
          }
        }
      }
    }
  }
</style>
