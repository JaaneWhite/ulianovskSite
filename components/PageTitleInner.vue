<template>
  <b-row class="page-title-row">
      <b-container class="page-title-cont">
        <b-row class="page-title">
          <b-col cols="12" md="3" class="link-col">
            <b-link class="page-title-link" :to="pageTitleLink.link">
              {{pageTitleLink.text}}
            </b-link>
          </b-col>
          <b-col cols="12" md="9" class="title-col">
            <b-row class="page-title-text">
              {{pageTitleText}}
            </b-row>
          </b-col>
        </b-row>
      </b-container>
  </b-row>
</template>

<script>
export default {
  name: "PageTitleInner",
  props: {
    pageTitleText: {},
    pageTitleLink: {},
  }
}
</script>

<style lang="scss">
/* по умолчанию -  мобильная версия - 0 - 767 px*/
@media (min-width: 0) {
  .page-title-row {
    background-image: url("~assets/img/bg.png");
    background-repeat: no-repeat;
    background-position: top;
    height: 220px;
    .page-title-cont {
      display: flex;
      .page-title {
        margin: auto auto auto 0;
        width: 100%;
        padding-left: 15px;
        flex-direction: column-reverse;
        .link-col {
          display: flex;
          margin-bottom: 30px;

          .page-title-link {
            margin-top: auto;
            margin-bottom: auto;
            background-image: url("~assets/img/arrow left w.png");
            background-repeat: no-repeat;
            background-position: left;
            padding-left: 15px;
            color: #ffffff;
            font-family: 'Roboto', sans-serif;
            font-size: 14px;
            font-weight: bold;
            text-decoration: underline;

          }
        }
        .title-col {
          margin-bottom: 30px;
          margin-top: 30px;
          .page-title-text {
            text-transform: uppercase;
            font-size: 16px;
            font-family: Oswald, sans-serif;
            color: #ffffff;
          }
        }
      }
    }
  }
}
/* планшетная версия - 768 - 1023 px*/
@media (min-width: 768px) {
  .page-title-row {
    height: 300px;
    .page-title-cont {
      .page-title {
        flex-direction: row;
        .link-col {
          margin-bottom: 0;
          .page-title-link {
            font-size: 16px;
          }
        }
        .title-col {
          margin-bottom: 0;
          margin-top: 0;
          .page-title-text {
            font-size: 20px;
          }
        }
      }
    }
  }
}
/* ПК версия -  от 1024 px*/
@media (min-width: 1024px) {
  .page-title-row {
    height: 360px;
    .page-title-cont {
      .page-title {
        .link-col {
          .page-title-link {
          }
        }
        .title-col {
          .page-title-text {
          }
        }
      }
    }
  }
}


</style>
