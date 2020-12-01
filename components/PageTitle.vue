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
    height: 180px;
    .page-title-cont {
      display: flex;
      .page-title {
        margin: auto auto auto 0;
        width: 100%;
        font-family: Oswald, sans-serif;
        font-size: 24px;
        color: #ffffff;
        font-weight: bold;
        text-transform: uppercase;

      }
    }
  }
}
/* планшетная версия - 768 - 1023 px*/
@media (min-width: 768px) {
  .page-title-row {
    height: 260px;
    .page-title-cont {
      .page-title {
        font-size: 36px;
        width: 75%;
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
