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
      <b-row style="padding-top: 30px; flex-direction: column">
        <b-form-radio-group class="search-radio" buttons>
          <b-form-group class="search-radio-line">
          <b-form-radio v-model="selected" class="search-radio-button" value="a">Фонды</b-form-radio>
          <b-form-radio v-model="selected" class="search-radio-button" value="b">Единицы хранения</b-form-radio>
          <b-form-radio v-model="selected" class="search-radio-button" value="c">Документы</b-form-radio>
          <b-form-radio v-model="selected" class="search-radio-button" value="d">Адресный указатель</b-form-radio>
          </b-form-group>
          <b-form-group class="search-radio-line">
          <b-form-radio v-model="selected" class="search-radio-button" value="e">Именной указатель</b-form-radio>
          <b-form-radio v-model="selected" class="search-radio-button" value="f">Источники комплектования</b-form-radio>
          </b-form-group>
        </b-form-radio-group>
        <b-form-group class="search-input-group">
          <b-row class="search-input-row">
            <b-col cols="12" md="4" style="display: flex">
              <div class="input-title">Архив</div>
            </b-col>
            <b-col cols="12" md="8" class="search-form-col">
              <b-dropdown
                split
                class="search-dd"
                split-class="search-dd-split"
                toggle-class="search-dd-toggle"
              >
                <b-dropdown-form>

                </b-dropdown-form>
              </b-dropdown>
            </b-col>
          </b-row>
          <b-row class="search-input-row">
            <b-col cols="12" md="4" style="display: flex">
              <div class="input-title">Шифр сайт</div>
            </b-col>
            <b-col cols="12" md="8" class="search-form-col">
              <b-form class="search-form">
                <b-form-input id="search-input" placeholder="" type="search"></b-form-input>
                <b-button class="search-button keyboard-button"></b-button>
              </b-form>
            </b-col>
          </b-row>
          <b-row class="search-input-row">
            <b-col cols="12" md="4" style="display: flex">
              <div class="input-title">Номер фонда</div>
            </b-col>
            <b-col cols="12" md="8" class="search-form-col">
              <b-form class="search-form">
                <b-form-input id="search-input" placeholder="" type="search"></b-form-input>
                <b-button class="search-button keyboard-button"></b-button>
              </b-form>
            </b-col>
          </b-row>
          <b-row class="search-input-row">
            <b-col cols="12" md="4" style="display: flex">
              <div class="input-title">Наименование</div>
            </b-col>
            <b-col cols="12" md="8" class="search-form-col">
              <b-form class="search-form">
                <b-form-input id="search-input" placeholder="" type="search"></b-form-input>
                <b-button class="search-button keyboard-button"></b-button>
              </b-form>
            </b-col>
          </b-row>
          <b-row class="search-input-row button-row">
                <b-button class="clean-button">Очистить</b-button>
                <b-button class="search-button sb-button"></b-button>
          </b-row>



        </b-form-group>


      </b-row>
    </b-tab>


    </b-tabs>
</template>
<script>
export default {
  name: 'SearchTabs',
  data() {
    return {
      selected: ''
    }
  }
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
      .search-radio {
        display: contents;
        .search-radio-line {
          margin-right: auto;
          margin-left: auto;
          margin-bottom: 0;
          .search-radio-button {
            background-color: transparent;
            border: none;
            border-radius: 0;
            font-family: Oswald, sans-serif;
            color: #949081;
            border-bottom: dashed #949081 2px;
            padding-bottom: 0;
            padding-left: 10px;
            padding-right: 10px;
            &.active {
              color: #474334;
              border-bottom: dashed #474334 2px;
            }
            &:hover {
              color: #9e0000;
              border-bottom: dashed #9e0000 2px;
            }
            input {
              display: none;
            }
          }

      }
      }
      .search-input-group {
        .search-input-row {
          margin-top: 20px;

        }
        .search-form-col {
          padding-right: 50px;
          .search-form {
            margin-left: 0;
            margin-bottom: 0;
            margin-top: 0;
            border: none;
          }
        }
        .input-title {
          margin: auto 0 auto auto;
          color: #474334;
          font-weight: bold;
        }
        .search-dd {
          width: 100%;
          height: 45px;

          .search-dd-split {
            width: 90%;
            border-radius: 0;
            background-color: white;
            border: none;
            box-shadow: none;

          }
          .dropdown-toggle::after {
            content: none;
          }
          .search-dd-toggle {
            width: 10%;
            border-radius: 0;
            background-color: white;
            border: none;
            box-shadow: none;
            padding: 0;
            background-image: url("~assets/svg/arrow down.svg");
            background-repeat: no-repeat;
            background-position: center;
            background-size: 50%;

            &[aria-expanded="true"] {
              background-image: url("~assets/svg/arrow up.svg");

            }



          }
        }
        .button-row {
          padding-right: 50px;
          justify-content: flex-end;
          padding-bottom: 20px;
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
          .clean-button {
            border-radius: 0;
            height: 45px;
            width: 90px;
            border: none;
            background-color: transparent;
            color: #949081;
            text-decoration: underline;
            &:hover, &:focus, &.active, &:active {
              box-shadow: none;
              color: #474334;
            }
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
