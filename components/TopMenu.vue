<template>
  <b-navbar toggleable="lg" class="top-menu-block" :class="navbarClass">
    <b-navbar-brand>
      <b-img src="~/assets/img/logo.png" class="logo-img" v-if="collapseExpanded === false" />
      <b-row class="logo-text" v-if="collapseExpanded === false">ГАУО</b-row>
      <b-row class="logo-text-expanded" v-if="autorized === false">Авторизуйтесь для получения услуг архива</b-row>
    </b-navbar-brand>

    <b-navbar-toggle target="nav-collapse" class="burger-button"></b-navbar-toggle>
    <b-collapse id="nav-collapse" is-nav @show="onCollapseSwitch" @hide="onCollapseSwitch" >
      <b-navbar-nav fill class="top-menu">
        <template v-if="autorized === false">
        <div class="user-block">
          <b-nav-item class="user-block-nav-item auth" to="">Вход или Регистрация</b-nav-item>
          <b-nav-item class="user-block-nav-item cart" to="">Корзина</b-nav-item>
          <b-nav-item class="user-block-nav-item contacts" to="contacts">Контакты</b-nav-item>
        </div>
        </template>
        <template v-else>
          <div class="user-block">
            <b-nav-item class="user-block-nav-item auth no-link">Здравствуйте,</b-nav-item>
            <b-nav-item-dropdown class="user-block-nav-item userName" to="" :text="userName">
              <b-dropdown-item to="#" class="user-menu-item">Активировать абонемент</b-dropdown-item>
              <b-dropdown-item to="#" class="user-menu-item">Купить абонемент</b-dropdown-item>
              <b-dropdown-item to="#" class="user-menu-item">Мои заказы</b-dropdown-item>
              <b-dropdown-item to="#" class="user-menu-item">Мои запросы</b-dropdown-item>
              <b-dropdown-item to="#" class="user-menu-item">Мои требования</b-dropdown-item>
              <b-dropdown-item to="#" class="user-menu-item">Мои данные</b-dropdown-item>
              <b-dropdown-item to="#" class="user-menu-item">Выйти</b-dropdown-item>
            </b-nav-item-dropdown>
            <b-nav-item class="user-block-nav-item cart" to="">Корзина</b-nav-item>
            <b-nav-item class="user-block-nav-item contacts" to="contacts">Контакты</b-nav-item>
          </div>
        </template>


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
      autorized: true,
      userName: 'Василий',
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
          margin-right: 30px;
          &.auth {
            background-image: url("~assets/svg/login.svg");
          }
          &.cart {
            background-image: url("~assets/svg/cart w.svg");
          }
          &.contacts {
            background-image: url("~assets/svg/contacts.svg");
            background-position-y: 10px;
            border-bottom: solid 1px #d96a6a;
            padding-bottom: 15px;
            margin-bottom: 15px;
          }
          &.no-link {
            a {
              text-decoration: none;
              padding-bottom: 0;
            }
          }
          &.userName {
            a {
              text-decoration: none;
              border-bottom: dashed white 1px;
              width: fit-content;
              padding-bottom: 0;
              padding-top: 0;
              padding-left: 0;
              margin-left: 30px;
            }
          }
          .dropdown-toggle::after {
            background-image: url("~assets/svg/arrow down w.svg");
            background-size: 10px;
            background-position: center;
            background-repeat: no-repeat;
            border: none;
            width: 15px;
            height: 15px;
            vertical-align: middle;
          }
          &.show {
            .dropdown-toggle::after {
              background-image: url("~assets/svg/arrow up w.svg");
            }

          }
          a {
            text-align: left;
            font-size: 14px;
            color: white;
            text-decoration: underline;
            padding-left: 30px;

          }
          .dropdown-menu {
            background-color: #a72c2c;
            margin-left: -30px;
            margin-right: -30px;
            border-radius: 0;
            border: none;
            padding-top: 15px;
            padding-bottom: 15px;
            .user-menu-item {
              font-size: 15px;
              margin-left: 30px;
              padding-top: 15px;
              padding-bottom: 15px;
              a{
                border: none;
              }



            }
          }

        }
      }

      .top-menu-item {
        border: none;
        box-shadow: none;

        .nav-link {
          font-size: 15px;
          color: #ffffff;
          height: 100%;
          display: flex;
          align-items: center;
          text-align: left;
          padding-right: 30px;
          padding-left: 30px;
          padding-bottom: 15px;
          padding-top: 15px;

        }

        .dropdown-toggle::after {
          background-image: url("~assets/svg/arrow down w.svg");
          background-size: 10px;
          background-position: center;
          background-repeat: no-repeat;
          border: none;
          width: 15px;
          height: 15px;
          vertical-align: middle;
          margin-left: auto;
        }
        &.show {
          .dropdown-toggle::after {
            background-image: url("~assets/svg/arrow up w.svg");
          }
          .nav-link {
            color: white;
            background-color: #c06a6a;
            border: none;
          }
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
            background-color: #a72c2c;
            padding: 0;
            flex-direction: column;
            text-align: left;
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
                  padding-left: 60px;
                  padding-top: 15px;
                  padding-bottom: 15px;

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


  .navbarExpanded {
   width: 50%;
    z-index: 50;
 }
  .top-menu-block {
    position: absolute;
    right: 0;
    top: 0;

    .navbar-brand {
      width: 65%;
      .logo-img {
        display: none;
      }
      .logo-text {
        display: none;
      }
    }
    .burger-button {
      margin-left: auto;
      margin-right: 15px;
      margin-top: 20px;
      width: 55px;
      height: 55px;
      padding: 0;
      .navbar-toggler-icon {
        width: 55px;
        height: 55px;
        background-image: url("~assets/img/menu open.png");
        background-size: 55px;

      }
      &.not-collapsed {
        .navbar-toggler-icon {
          width: 55px;
          height: 55px;
          background-image: url("~assets/img/menu close.png");
          background-size: 55px;

        }
      }
    }
    .top-menu {
      .user-block {
        margin-top: -20px;
        .no-link {
          margin-top: -20px;
        }
      }
    }
  }
}
/* ПК версия -  от 1024 px*/
@media (min-width: 1024px) {
  .top-menu-block {
    position: relative;
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
          background-color: white;
          color: #474334;

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
        &.show {
          .nav-link {
            background-color: #9e0000;
          }
        }
        .dropdown-menu {
          position: fixed;
          background-color: #9e0000;
          .dropdown-menu-container {
            text-align: left;
            background-color: #9e0000;
            .dd-menu-row {
              width: 100%;
              margin: 30px 50px;
              .dd-menu-col {

                .dropdown-item {
                  padding-top: 15px;
                  padding-bottom: 15px;
                  padding-left: 0;

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
