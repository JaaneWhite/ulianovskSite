<template>
  <b-breadcrumb :items="breadCrumbItems"></b-breadcrumb>
</template>

<script>
export default {
  name: "BreadCrumbs",
  props: {
    breadCrumbItems: {}
  }
}
</script>

<style lang="scss">
/* по умолчанию -  мобильная версия - 0 - 767 px*/
@media (min-width: 0) {
  .breadcrumb {
    padding: 0;
    padding-top: 15px;
    padding-bottom: 15px;
    padding-left: 15px;
    margin-bottom: 0;
    background-color: transparent;
    border-radius: 0;
    border: none;

    .breadcrumb-item {
      font-size: 14px;
      font-family: 'Roboto', sans-serif;
      font-style: italic;
      color: #949182;
      line-height: 1.2;

      a {
        color: #949182;
        text-decoration: underline;

        &:hover {
          color: #9e0000;
        }
      }
      + .breadcrumb-item {
        &::before {
          display: inline-block; // Suppress underlining of the separator in modern browsers
          content: ">";

        }
      }


    }
  }
}
/* планшетная версия - 768 - 1023 px*/
@media (min-width: 768px) {
  .breadcrumb {
    padding: 0;
    padding-top: 30px;
    padding-bottom: 30px;
  }
}
/* ПК версия -  от 1024 px*/
@media (min-width: 1024px) {
  .breadcrumb {
    padding: 0;
    padding-top: 30px;
    padding-bottom: 30px;
  }
}
</style>
