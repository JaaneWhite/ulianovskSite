<template>
  <b-navbar toggleable="lg" class="top-menu-block" :class="navbarClass">
    <b-navbar-brand>
      <b-img src="~/assets/img/logo.png" class="logo-img" v-if="collapseExpanded === false" />
      <b-row class="logo-text" v-if="collapseExpanded === false">ГАУО</b-row>
      <b-row class="logo-text-expanded" v-else>Авторизуйтесь для получения услуг архива</b-row>
    </b-navbar-brand>

    <b-navbar-toggle target="nav-collapse" class="burger-button"></b-navbar-toggle>
    <b-collapse id="nav-collapse" is-nav @show="onCollapseSwitch" @hide="onCollapseSwitch" >
      <b-navbar-nav fill class="top-menu">
        <div class="user-block">
          <b-nav-item class="user-block-nav-item auth" to="">Вход или Регистрация</b-nav-item>
          <b-nav-item class="user-block-nav-item cart" to="">Корзина</b-nav-item>
          <b-nav-item class="user-block-nav-item contacts" to="contacts">Контакты</b-nav-item>
        </div>


        <b-nav-item-dropdown href="#" class="top-menu-item" text="Путеводители">
          <b-container class="dropdown-menu-container">
            <b-row class="dd-menu-row">
              <b-col cols="12" xl="6" class="dd-menu-col">
                <b-dropdown-item to="funds">Фонды досоветского периода</b-dropdown-item>
              </b-col>
              <b-col cols="12" xl="6" class="dd-menu-col">
                <b-dropdown-item to="404">Фонды советского периода</b-dropdown-item>
              </b-col>
            </b-row>
          </b-container>
        </b-nav-item-dropdown>
        <b-nav-item-dropdown href="#" class="top-menu-item" text="Указатели">
          <b-container class="dropdown-menu-container">
            <b-row class="dd-menu-row">
              <b-col cols="12" xl="6" class="dd-menu-col">
                <b-dropdown-item to="#">Именной</b-dropdown-item>
              </b-col>
              <b-col cols="12" xl="6" class="dd-menu-col">
                <b-dropdown-item to="#">Географический</b-dropdown-item>
              </b-col>
            </b-row>

          </b-container>
        </b-nav-item-dropdown>
        <b-nav-item to="#" class="top-menu-item">Муниципальные архивы <br> Ульяновской области</b-nav-item>
        <b-nav-item-dropdown to="#" class="top-menu-item" text="Тематические базы данных">
          <b-container class="dropdown-menu-container">
            <b-row class="dd-menu-row">
              <b-col cols="12" xl="4" class="dd-menu-col">
                <b-dropdown-item to="#">Каталог изданий</b-dropdown-item>
                <b-dropdown-item to="#">Уставные грамоты</b-dropdown-item>
                <b-dropdown-item hto="#">Фотокаталог</b-dropdown-item>
                <b-dropdown-item to="#">Справочники АТД</b-dropdown-item>
              </b-col>
              <b-col cols="12" xl="4" class="dd-menu-col">
                <b-dropdown-item to="#">Справочно-информационный фонд архива</b-dropdown-item>
                <b-dropdown-item to="#">Клировые ведомости</b-dropdown-item>
                <b-dropdown-item to="#">Награжденные</b-dropdown-item>
              </b-col>
              <b-col cols="12" xl="4" class="dd-menu-col">
                <b-dropdown-item to="#">Перепись населения</b-dropdown-item>
                <b-dropdown-item to="#">Ревизские сказки</b-dropdown-item>
                <b-dropdown-item to="#">Фотокаталог</b-dropdown-item>
              </b-col>
            </b-row>
          </b-container>
        </b-nav-item-dropdown>
        <b-nav-item-dropdown href="#" class="top-menu-item" text="Услуги">
          <b-container class="dropdown-menu-container">
            <b-row class="dd-menu-row">
              <b-col cols="12" xl="4" class="dd-menu-col">
                <b-dropdown-item to="service">Социально-правовые и тематические запросы</b-dropdown-item>
                <b-dropdown-item to="#">Обслуживание пользователей в читальном зале</b-dropdown-item>
                <b-dropdown-item to="#">Приём документов от организаций, являющихся источниками комплектования архива</b-dropdown-item>
              </b-col>
              <b-col cols="12" xl="4" class="dd-menu-col">
                <b-dropdown-item to="#">Составление информационных документов</b-dropdown-item>
                <b-dropdown-item to="#">Проведение информационных мероприятий</b-dropdown-item>
                <b-dropdown-item to="#">Предоставление документов организациям для экспонирования</b-dropdown-item>
              </b-col>
              <b-col cols="12" xl="4" class="dd-menu-col">
                <b-dropdown-item to="#">Копирование документов и печатных изданий</b-dropdown-item>
                <b-dropdown-item to="#">Обеспечение сохранности и упорядочение документов организаций</b-dropdown-item>
              </b-col>
            </b-row>
          </b-container>
        </b-nav-item-dropdown>
        <b-nav-item-dropdown to="#" class="top-menu-item" text="Об архиве">
          <b-container class="dropdown-menu-container">
            <b-row class="dd-menu-row">
              <b-col cols="12" xl="4" class="dd-menu-col">
                <div class="dd-menu-item-title">Общие сведения</div>
                <b-dropdown-item to="#">История архива, Правовые документы</b-dropdown-item>
                <b-dropdown-item to="#">Список муниципальных архивов Ульяновской области, Вакансии</b-dropdown-item>
              </b-col>
              <b-col cols="12" xl="4" class="dd-menu-col">

            <div class="dd-menu-item-title">Деятельность</div>
            <b-dropdown-item to="#">Рассекречивание</b-dropdown-item>
            <b-dropdown-item to="#">Планы развития архивного дела</b-dropdown-item>
            <b-dropdown-item to="#">Отчеты о выполнении плана развития архивного дела</b-dropdown-item>
            <b-dropdown-item to="#">Антикоррупционная деятельность</b-dropdown-item>
              </b-col>
              <b-col cols="12" xl="4" class="dd-menu-col">
            <b-dropdown-item to="#">Источники комплектования</b-dropdown-item>
            <b-dropdown-item to="#">Отчёт о проведении специальной оценки условий труда</b-dropdown-item>
            <b-dropdown-item to="#">Планы мероприятий по охране труда</b-dropdown-item>
              </b-col>
            </b-row>
          </b-container>
        </b-nav-item-dropdown>
        <b-nav-item to="contacts" class="top-menu-item" text="">Контакты</b-nav-item>
      </b-navbar-nav>
    </b-collapse>

  </b-navbar>
</template>

<script>
export default {
  name: "TopMenu",
  data() {
    return {
      collapseExpanded: false,
      navbarClass: '',
    }
  },

  methods: {
    onCollapseSwitch: function () {
      if (this.collapseExpanded === false) {
        this.collapseExpanded = true;
        this.navbarClass = 'navbarExpanded';

      } else {
        this.collapseExpanded = false;
        this.navbarClass = '';
      }
    }
  }

}
</script>

<style lang="scss">
/* по умолчанию -  мобильная версия - 0 - 767 px*/
@media (min-width: 0) {
  .top-menu-block {
    width: 100%;
    padding-right: 0;
    padding-left: 0;
    justify-content: space-between;
    .navbar-brand {
      display: flex;
      margin-left: 15px;
      width: 70%;
      .logo-img {
        width: 57px;
        height: 45px;
      }
      .logo-text {
        font-family: 'Oswald', sans-serif;
        font-size: 24px;
        font-weight: bold;
        text-transform: uppercase;
        line-height: 1.5;
        text-align: left;
        padding-left: 15px;
        margin-top: auto;
        margin-bottom: auto;
      }
      .logo-text-expanded {
        width: 80%;
      }
    }
    &.navbarExpanded {
      background-color: #9e0000;
      .logo-text-expanded {
        font-size: 13px;
        color: white;
        font-style: italic;
        white-space: normal;
      }
    }
    .burger-button {
      margin-right: 0;
      border: none;
      border-radius: 0;
      outline: none;
      &:hover, &:focus, &:active, &.active {
        border-radius: 0;
        border: none;
        outline: none;
      }
      .navbar-toggler-icon {
        background-image: url("~assets/img/menu open.png");
      }
      &.not-collapsed {
        .navbar-toggler-icon {
          background-image: url("~assets/img/menu close.png");
        }
      }
    }
    .navbar-collapse {
      .user-block {
        display: none;
      }
      &.show {
        .user-block {
          display: flex;
        }
      }
    }


    .top-menu {
      width: 100%;
      .user-block {
        flex-direction: column;
        padding-left: 30px;
        .user-block-nav-item {
          background-repeat: no-repeat;
          background-size: 16px;
          background-position-y: center;
          padding-left: 30px;

          &.auth {
            background-image: url("~assets/svg/login.svg");
          }
          &.cart {
            background-image: url("~assets/svg/cart w.svg");
          }
          &.contacts {
            background-image: url("~assets/svg/contacts.svg");
          }


          a {
            text-align: left;
            font-size: 14px;
            color: white;
            text-decoration: underline;

          }

        }
      }

      .top-menu-item {
        border: none;
        box-shadow: none;
        .nav-link {
          font-size: 15px;
          color: #474334;
          height: 100%;
          display: flex;
          align-items: center;
          text-align: left;
          border-bottom: solid 1px #949081;
          padding-right: 15px;
          padding-left: 15px;

        }
        &.show {
          .nav-link {
            color: white;
            background-color: #9e0000;
            border: none;
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
          left: 0;
          right: 0;
          top: auto;
          width: 100%;
          opacity: 100%;
          .dropdown-menu-container {
            background-color: #9e0000;
            padding: 0;
            flex-direction: column;
            text-align: right;
            align-items: flex-end;
            .dd-menu-row {
              .dd-menu-col {
                padding: 0;
                .dropdown-item {
                  color: white;
                  font-size: 15px;
                  line-height: 1.733;
                  white-space: normal;
                  width: 100%;

                  &:hover {
                    color: #daa3a3;
                    background-color: transparent;
                  }

                }
                .dd-menu-item-title {
                  color: #daa3a3;
                  font-size: 15px;
                  width: 100%;
                  border-bottom: #daa3a3 solid 1px;
                  text-align: left;
                  padding-left: 30px;
                  padding-top: 15px;

                }
              }
            }
          }
        }
      }
    }
  }
}
/* планшетная версия - 768 - 1023 px*/
@media (min-width: 768px) {

}
/* ПК версия -  от 1024 px*/
@media (min-width: 1024px) {
  .top-menu-block {
    justify-content: space-between;
    padding-bottom: 0;
    .navbar-brand {
      display: none;
    }

    .top-menu {
      height: 50px;

      .top-menu-item {
        height: 100%;
        .nav-link {
          border: none;

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
        .dropdown-toggle::after {
          display: none;
        }
        .dropdown-menu {
          position: fixed;
          background-color: #9e0000;
          .dropdown-menu-container {
            text-align: left;
            .dd-menu-row {
              width: 100%;
              margin: 30px 50px;
              .dd-menu-col {

                .dropdown-item {
                  padding-top: 15px;
                  padding-bottom: 15px;

                }
                .dd-menu-item-title {
                  display: none;
                }
              }
            }
          }
        }
      }
    }
  }
}





</style>
