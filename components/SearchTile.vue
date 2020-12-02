<template>
  <b-row class="search-tile">
    <div class="search-title">{{searchTileTitle}}</div>
    <b-form class="search-form">
      <b-form-input id="search-input" placeholder="Введите номер фонда и/или слово в названии..." type="search"></b-form-input>
      <b-button class="search-button keyboard-button"></b-button>
      <b-button class="search-button sb-button"></b-button>
    </b-form>
  </b-row>
</template>

<script>
export default {
  name: "SearchTile",
  props: {
    searchTileTitle: {}
  }
}
</script>

<style lang="scss" scoped>
.search-tile {
  background-color: #ede9da;

  .search-title {
    padding-top: 30px;
    font-size: 30px;
    font-family: "Oswald", sans-serif;
    color: rgb(71, 67, 52);
    font-weight: bold;
    text-transform: uppercase;
    line-height: 1.2;
    text-align: left;
    margin-right: auto;
    margin-left: 5%;
  }

  .search-form {
    margin-left: 5%;
    margin-right: 5%;
    margin-top: 30px;
    margin-bottom: 30px;
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
      color: #949081;
      font-size: 13px;

      &::-webkit-input-placeholder {
        color: #949081;
        font-style: italic;
        font-size: 13px;
        line-height: 1.2;

      }

      &::-moz-placeholder {
        color: #949081;
        font-style: italic;
        font-size: 13px;
        line-height: 1.2;

      }
    }

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

</style>
