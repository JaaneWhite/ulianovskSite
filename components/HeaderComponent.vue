<template>
  <header>
    <b-row class="header-top-row">
      <b-container>
        <b-row>
          <b-col cols="" xl="2" class="logo-block">
            <b-img src="~/assets/img/logo.png"></b-img>
          </b-col>
          <b-col cols="" xl="10" class="header-title-block">
            <b-row class="title-row">
              <b-col cols="" xl="9" class="title-text">
                Государственный архив Ульяновской области
              </b-col>
              <b-col cols="" xl="3" class="login-block">
                <b-row class="login-title">
                  Авторизуйтесь для получения услуг архива
                </b-row>
                <b-row>
                  <b-col cols="" xl="4" class="login-links cart">
                    <b-button to="" class="cart-link">Корзина</b-button>

                  </b-col>
                  <b-col cols="" xl="8" class="login-links auth">
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

    }

    .header-title-block {
      padding: 0;

      .title-row {
        .title-text {
          font-family: 'Oswald', sans-serif;
          font-size: 24px;
          font-weight: bold;
          text-transform: uppercase;
          line-height: 1.5;
          text-align: left;
          padding-left: 0;
        }

        .login-block {
          color: #949081;
          text-align: right;
          padding: 0;

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
      }
    }
  }



</style>
