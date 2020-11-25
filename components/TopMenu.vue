<template>
  <b-navbar toggleable="lg" class="top-menu-block">
    <b-navbar-toggle target="nav-collapse" class="burger-button"></b-navbar-toggle>
    <b-collapse id="nav-collapse" is-nav >
      <b-navbar-nav fill class="top-menu">
        <b-nav-item-dropdown href="#" class="top-menu-item" text="Путеводители">

          <b-container class="dropdown-menu-container">
          <b-dropdown-item href="#">Фонды досоветского периода</b-dropdown-item>
          <b-dropdown-item href="#">Фонды советского периода</b-dropdown-item>
          </b-container>

        </b-nav-item-dropdown>
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

<style lang="scss">
  .top-menu-block {
    width: 100%;
    padding-right: 0;
    padding-left: 0;

    .top-menu {
      width: 100%;
      height: 50px;

      .top-menu-item {
        height: 100%;
        border: none;
        box-shadow: none;
        .nav-link {
          font-size: 15px;
          color: #474334;
          height: 100%;
          display: flex;
          align-items: center;
          text-align: center;

          &:hover {
            font-size: 15px;
            color: white;
            background-color: #9e0000;
          }
          &:focus {
            border: none;
            box-shadow: none;
            outline: none;
          }

        }
        &.show {
          .nav-link {
            color: white;
            background-color: #9e0000;
          }

      }
        .dropdown-toggle::after {
          display: none;
        }
        .dropdown-menu {
          border: none;
          border-radius: 0;
          margin: 0;
          padding: 0;
          position: fixed;
          left: 0;
          right: 0;
          top: auto;
          width: 100%;
          .dropdown-menu-container {
            background-color: #9e0000;
            padding: 0;

            .dropdown-item {
              color: white;
              font-size: 15px;
              line-height: 1.733;

              &:hover {
                color: #daa3a3;
                background-color: transparent;
              }

            }
          }
          }
        }
      }
    }

</style>
