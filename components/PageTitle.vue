<template>
  <b-row class="page-title-row">
      <b-container class="page-title-cont">
        <b-row class="page-title">
          {{pageTitleText}}
        </b-row>
      </b-container>
  </b-row>
</template>

<script>
export default {
  name: "PageTitle",
  props: {
    pageTitleText: {}
  }
}
</script>

<style lang="scss" scoped>
/* по умолчанию -  мобильная версия - 0 - 767 px*/
@media (min-width: 0) {
  .page-title-row {
    background-image: url("~assets/img/bg.png");
    background-repeat: no-repeat;
    background-position: top;
    height: 190px;
    .page-title-cont {
      display: flex;
      .page-title {
        margin: auto auto auto 0;
        width: 100%;
        font-family: Oswald, sans-serif;
        font-size: 20px;
        color: #ffffff;
        font-weight: bold;
        text-transform: uppercase;
        padding-left: 15px;

      }
    }
  }
}
/* планшетная версия - 768 - 1023 px*/
@media (min-width: 768px) {
  .page-title-row {
    height: 340px;
    .page-title-cont {
      .page-title {
        font-size: 36px;
        width: 75%;
        padding-left: 0;
      }
    }
  }
}
/* ПК версия -  от 1024 px*/
@media (min-width: 1024px) {
  .page-title-row {
    height: 340px;
    .page-title-cont {
      .page-title {
        font-size: 46px;
        width: 50%;
      }
    }
  }
}


</style>
