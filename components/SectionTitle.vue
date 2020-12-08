<template>
  <b-row class="section-title">{{sectionTitleText}}</b-row>
</template>

<script>
export default {
  name: "SectionTitle",
  props: {
    sectionTitleText: {}
  }
}
</script>

<style lang="scss">
/* по умолчанию -  мобильная версия - 0 - 767 px*/
@media (min-width: 0) {
  .section-title {
    font-size: 30px;
    font-family: 'Oswald', sans-serif;
    color: #474335;
    padding-left: 15px;
    margin-left: 0;
    padding-top: 15px;
    padding-bottom: 15px;
    line-height: 1.2;
    text-transform: uppercase;
    font-weight: bold;
    &.fs-sm {
      font-size: 24px;
      padding-top: 20px;
    }
    &.bg-1 {
      background: url("~assets/svg/decor 1.svg") left no-repeat;
      background-size: 70px;
      background-position-y: top;
    }
    &.bg-2 {
      background: url("~assets/svg/decor 2.svg") left no-repeat;
      background-size: 75px;
      background-position-y: top;
      padding-left: 30px;
      margin-left: -15px;
    }
    &.bg-3 {
      background: url("~assets/svg/decor 3.svg") left no-repeat;
      background-size: 70px;
      background-position-y: top;
    }
    &.bg-4 {
      background: url("~assets/svg/decor 4.svg") left no-repeat;
      background-size: 80px;
      background-position-y: top;
      padding-left: 25px;
      margin-left: -10px;
    }

  }
}
/* планшетная версия - 768 - 1023 px*/
@media (min-width: 768px) {
  .section-title {
    font-size: 30px;
    margin-left: -20px;
    margin-bottom: 15px;
    width: 100%;
    padding: 15px 0 15px 20px;

    &.bg-1 {
      background-size: 100px;
      background-position-y: center;
    }

    &.bg-2 {
      background: url("~assets/svg/decor 2.svg") left no-repeat;
      background-size: 100px;
      background-position-y: center;
      padding-left: 30px;
      margin-left: -30px;
    }

    &.bg-3 {
      background: url("~assets/svg/decor 3.svg") left no-repeat;
      background-size: 100px;
      background-position-y: center;
    }

    &.bg-4 {
      background: url("~assets/svg/decor 4.svg") left no-repeat;
      background-size: 100px;
      background-position-y: center;
    }

  }
}
/* ПК версия -  от 1024 px*/
@media (min-width: 1024px) {

  .section-title {
    font-size: 40px;
    &.bg-1 {

    }

    &.bg-2 {

    }

    &.bg-3 {

    }

    &.bg-4 {
      padding-left: 30px;
      margin-left: -30px;
    }

  }

}

</style>
