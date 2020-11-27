<template>
  <b-tabs class="search-tabs" fill>
    <b-tab title="Быстрый поиск">
      <b-row>
      <div class="search-title">ПОИСК ДОКУМЕНТОВ</div>
      <b-form class="search-form">
        <b-form-input id="search-input" placeholder="Найти нужное" type="search"></b-form-input>
        <b-button class="search-button keyboard-button"></b-button>
        <b-button class="search-button sb-button"></b-button>
      </b-form>
      </b-row>
    </b-tab>
    <b-tab title="Расширенный поиск">
      <b-row>

      </b-row>
    </b-tab>


    </b-tabs>
</template>
<script>
export default {
  name: 'SearchTabs'
}
</script>
<style lang="scss">
/* по умолчанию -  мобильная версия - 0 - 767 px*/
@media (min-width: 0) {
  .search-tabs {
    margin: auto;
    width: 100%;
    .nav-tabs {
      border: none;
      .nav-item {
        .nav-link {
          background-color: #e4dfcb;
          font-size: 14px;
          font-weight: bold;
          text-transform: uppercase;
          color: #949081;
          border: none;
          border-radius: 0;
          padding-top: 30px;
          padding-bottom: 30px;

          &.active {
            background-color: #ede9da;
            color: #474334;

          }
        }
      }
    }
    .tab-content {
      background-color: #ede9da;
      .search-title {
        padding-top: 60px;
        font-size: 30px;
        font-family: "Oswald",sans-serif;
        color: rgb(71, 67, 52);
        font-weight: bold;
        text-transform: uppercase;
        line-height: 1.2;
        text-align: center;
        margin-right: auto;
        margin-left: auto;
      }
      .search-form {
        margin-left: 10%;
        margin-right: 10%;
        margin-top: 50px;
        margin-bottom: 60px;
        width: 100%;
        display: flex;
        flex-direction: row;
        background: white;
        border: solid #e4dfcb 1px;
        border-radius: 0;
        #search-input {
          height: 45px;
          border-radius: 0;
          box-shadow: none;
          width: 100%;
          border: none;
        }
        .keyboard-button {
          border-radius: 0;
          height: 45px;
          margin-right: 10px;
          border: none;
          background-color: transparent;
          background-image: url("~assets/svg/keyboard.svg");
          background-repeat: no-repeat;
          background-position: center;

        }
        .sb-button {
          border-radius: 0;
          height: 45px;
          width: 65px;
          border: none;
          background-color: #9e0000;
          background-image: url("~assets/img/search.png");
          background-repeat: no-repeat;
          background-position: center;
          &:hover, &:focus, &.active, &:active {
            background-color: #c10000;
            box-shadow: none;
          }
        }

      }

    }

  }
}

@media (min-width: 768px) {
  .search-tabs {
    margin: auto;
    width: 640px;
  }
}

@media (min-width: 1024px) {


}
</style>
