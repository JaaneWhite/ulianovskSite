<template>
  <header>
    <b-row >
      <b-container>
        <b-row class="header-top-row">
          <b-col cols="0" md="0" xl="2" class="logo-block">
            <b-img src="~/assets/img/logo.png" class="logo-img"></b-img>
          </b-col>
          <b-col cols="12" md="12" xl="10" class="header-title-block">
            <b-row class="title-row">
              <b-col cols="12" md="8" xl="9" class="title-text">
                <b-row class="md">Государственный архив Ульяновской области</b-row>
                <b-row class="sm">ГАУО</b-row>
              </b-col>
              <b-col cols="12" md="0" xl="3" class="login-block">
                <b-row class="login-title">
                  Авторизуйтесь для получения услуг архива
                </b-row>
                <b-row>
                  <b-col cols="4" xl="4" class="login-links cart">
                    <b-button to="" class="cart-link">Корзина</b-button>

                  </b-col>
                  <b-col cols="8" xl="8" class="login-links auth">
                    <b-dropdown text="Вход или регистрация"
                                class="auth-button">
                      <b-dropdown-item href="#">Вход</b-dropdown-item>
                      <b-dropdown-item href="#">Регистрация</b-dropdown-item>
                    </b-dropdown>

                  </b-col>
                </b-row>
              </b-col>
            </b-row>
            <b-row class="menu-row">
              <top-menu />
            </b-row>
          </b-col>
        </b-row>
      </b-container>

    </b-row>
  </header>
</template>

<script>
import TopMenu from "~/components/TopMenu";
export default {
  name: "HeaderComponent",
  components: {TopMenu}
}
</script>

<style lang="scss">
/* по умолчанию -  мобильная версия - 0 - 767 px*/
@media (min-width: 0) {
  .header-top-row {
    .logo-block {
      display: none;
      padding: 0;
      .logo-img {
        margin: auto;
        width: 100%;
      }
    }

    .header-title-block {
      padding: 0;
      display: flex;
      flex-direction: row;
      justify-content: space-between;

      .title-row {
        .title-text {
          font-family: 'Oswald', sans-serif;
          font-size: 24px;
          font-weight: bold;
          text-transform: uppercase;
          line-height: 1.5;
          text-align: left;
          padding-left: 15px;
          margin-top: auto;
          margin-bottom: auto;
          display: none;
        }

        .login-block {
          display: none;
          color: #949081;
          text-align: right;
          padding: 0 15px;
          margin-top: 15px;

          .login-title {
            font-style: italic;
            font-size: 13px;
            display: block;
            text-align: right;
            padding-bottom: 10px;
          }

          }

          & .cart {
            background-image: url("~assets/svg/cart.svg");
            background-position: left;
            background-repeat: no-repeat;
            background-size: 20%;
            text-align: left;
            padding-left: 25px;
            .cart-link {
              color: #949081;
              font-size: 14px;
              text-decoration: none;
              text-align: left;
              background-color: transparent !important;
              border-radius: 0;
              border: none;
              padding: 0;
              box-shadow: none;
              border-bottom: dotted 2px #949081;
              &:hover {
                color: #9e0000;
                border-bottom: solid 2px #9e0000;
              }
            }


          }

          & .auth {
            text-align: right;
            background-image: url("~assets/svg/arrow down.svg");
            background-position: right;
            background-repeat: no-repeat;
            background-size: 5%;
            &:hover {
              background-image: url("~assets/svg/arrow down b.svg");
              background-position: right;
              background-repeat: no-repeat;
              background-size: 5%;
            }

            .auth-button {
              .btn-secondary {
                background-color: transparent !important;
                border-radius: 0;
                border: none;
                color: #949081;
                font-size: 14px;
                padding: 0;

                box-shadow: none;
                border-bottom: dotted 2px #949081;
                &:hover {
                  color: #9e0000;
                  border-bottom: solid 2px #9e0000;
                }
              }
              .dropdown-toggle::after {
                display: none;
              }
            }
          }
        }
      .menu-row {
      width: 100%}
    }
    }
  }
/* планшетная версия - 768 - 1023 px*/
@media (min-width: 768px) {
  .header-top-row {
    .logo-block {
      .logo-img {
        margin: 30px auto;
        width: auto;
      }

    }
    .header-title-block {
      padding: 0;
      .title-row {
        .title-text {
          padding-left: 15px;

          .sm {
            display:none;
          }
          .md {
            display: flex;
          }
        }
        .login-block {
        }
        & .cart {
          padding-left: 25px;
          .cart-link {
            font-size: 13px;
          }
        }
        & .auth {
          .auth-button {
            .btn-secondary {
              font-size: 13px;
            }
          }
        }
      }
    }
  }
}

/* ПК версия -  от 1024 px*/
@media (min-width: 1024px) {
    .header-top-row {
      .logo-block {
        display: flex;
        .logo-img {
          width: 109px;
          height: 86px;
          margin-left: 0;
        }
      }
      .header-title-block {
        padding: 0;
        flex-direction: column;
        .title-row {
          .title-text {
            margin-top: 30px;
            display: flex;
            .md {
              display: flex;
            }
          }
          .login-block {
            display: block;
            padding: 0;
            .login-title {
              padding-bottom: 10px;
            }
          }
          & .cart {
            .cart-link {
              font-size: 14px;
            }
          }
          & .auth {
            .auth-button {
              .btn-secondary {
                font-size: 14px;
              }
            }
          }
        }
      }
    }
  }
</style>
