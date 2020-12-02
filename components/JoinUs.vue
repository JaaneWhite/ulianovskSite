<template>
<b-row class="join-us-row">
  <b-container>
    <b-row class="join-us-content">
      <b-col cols="12" md="8" xl="8" class="text-col">
        <b-row class="join-us-text">
          <p class="t1">присоединяйтесь к нам,</p>
          <p class="t2">чтобы быть в курсе важных новостей</p>
        </b-row>
      </b-col>
      <b-col cols="12" md="4" xl="4" class="button-col">
        <b-button to="#" class="join-us-button">Зарегистрироваться</b-button>
      </b-col>
    </b-row>
  </b-container>

</b-row>
</template>

<script>
export default {
  name: "JoinUs"
}
</script>

<style lang="scss">
/* по умолчанию -  мобильная версия - 0 - 767 px*/
@media (min-width: 0) {
  .join-us-row {
    height: 200px;
    background-color: #ede9da;
    .container {
      display: flex;
      .join-us-content {
        margin-left: auto;
        margin-right: auto;
        height: 100%;
        background-image: url("~assets/img/decor tro.png");
        background-position: left;
        background-repeat: no-repeat;
        .text-col {
          padding: 0;
          padding-left: 40px;
          display: flex;
          .join-us-text {
            font-family: 'Oswald', sans-serif;
            color: #474334;
            font-weight: bold;
            text-transform: uppercase;
            line-height: 1.3;
            margin-top: auto;
            margin-bottom: auto;
            .t1 {
              font-size: 20px;
              margin-bottom: 0;
            }
            .t2 {
              font-size: 18px;
              margin-bottom: 0;
            }
          }
        }
        .button-col {
          padding: 0;
          display: flex;
          .join-us-button {
            margin-top: auto;
            margin-bottom: auto;
            margin-left: auto;
            margin-right: auto;
            padding-top: 12px;
            padding-bottom: 12px;
            width: 260px;
            background-color: #9e0000;
            color: white;
            font-size: 16px;
            font-weight: bold;
            border: none;
            box-shadow: none;
            border-radius: 0;
            &:hover {
              background-color: transparent;
              color: #9e0000;
            }
          }
        }
      }
    }
  }
}
/* планшетная версия - 768 - 1023 px*/
@media (min-width: 768px) {
  .join-us-row {
    height: 160px;

    .container {
      .join-us-content {
          .text-col {
            .join-us-text {
              .t1 {
                font-size: 22px;
              }

              .t2 {
                font-size: 20px;
              }
            }
          }
        .button-col {
          padding: 0;
          display: flex;

          .join-us-button {
            margin-top: auto;
            margin-bottom: auto;
            margin-left: auto;
            margin-right: 0;


          }
        }
      }
    }
  }
}
/* ПК версия -  от 1024 px*/
@media (min-width: 1024px) {
  .join-us-row {

    .container {
      .join-us-content {
        .text-col {
          .join-us-text {
            .t1 {
              font-size: 26px;
            }

            .t2 {
              font-size: 24px;
            }
          }
        }
      }
    }
  }
}
</style>
