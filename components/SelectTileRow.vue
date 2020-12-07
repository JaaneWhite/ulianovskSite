<template>
  <b-row class="select-tile-row">
    <div class="select-tile" v-for="selectTile in selectTiles">
      <div class="select-text" :to="selectTile.link">
        {{selectTile.text}}
      </div>
      <b-button class="select-close-button"></b-button>
    </div>
  </b-row>
</template>
<script>
export default {
  name: 'selectTileRow',
  props: {
    selectTiles: {}
  }
}
</script>
<style lang="scss">
/* по умолчанию -  мобильная версия - 0 - 767 px*/
@media (min-width: 0) {
  .select-tile-row {
    display: flex;
    flex-direction: row;
    margin-top: 15px;
    margin-bottom: 15px;

    .select-tile {
      display: flex;
      flex-direction: row;
      background-color: #efeada;
      margin-top: 15px;
      margin-bottom: 15px;
      margin-right: 15px;
      padding-top: 10px;
      padding-bottom: 10px;
      padding-left: 20px;
      padding-right: 10px;

      .select-text {
        color: #939182;
        font-size: 14px;


      }
      .select-close-button, .select-close-button:hover, .select-close-button:active, .select-close-button:focus, .select-close-button.active   {
        background-color: transparent;
        background-image: url("~assets/svg/cross.svg");
        background-size: 10px;
        background-position: center;
        background-repeat: no-repeat;
        border-radius: 0;
        border: none;
        margin-left: 10px;
        box-shadow: none;


      }
    }
  }
}

/* планшетная версия - 768 - 1023 px*/
@media (min-width: 768px) {
}

/* ПК версия -  от 1024 px*/
@media (min-width: 1024px) {
}

</style>
