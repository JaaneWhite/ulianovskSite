<template>
  <b-row class="case-tile">
    <b-col cols="12" md="12" xl="9" class="case-tile-info-col">
      <b-row class="case-tile-title">
        <b-link :to="caseItem.link">{{caseItem.code}}
          <b-img src="~assets/img/folder.png"></b-img>
        </b-link>
      </b-row>
      <b-row class="case-tile-info">
        <b-col cols="12" md="4">{{'Номер дела: '+ caseItem.number}}</b-col>
        <b-col cols="12" md="8">{{caseItem.scanned}}</b-col>
      </b-row>
    </b-col>
    <b-col cols="12" md="12" xl="3" class="case-tile-button-col">
      <b-button class="case-tile-button read">
        <div>Читать дело</div>
      </b-button>
      <b-button class="case-tile-button copy">
        <div>Заказать копию</div>
      </b-button>
      <b-button class="case-tile-button ask">
        <div>Подать требование</div>
      </b-button>
    </b-col>

  </b-row>
</template>
<script>
export default {
  name: 'caseTile',
  props: {
    caseItem: {}
  }
}
</script>
<style lang="scss">
/* по умолчанию -  мобильная версия - 0 - 767 px*/
@media (min-width: 0) {
  .case-tile {
    border-top: solid #e4dfcb 1px;
    border-bottom: solid #e4dfcb 1px;
    margin-top: 30px;
    font-size: 14px;
    .case-tile-info-col {
      .case-tile-title {
        border-bottom: solid #e4dfcb 1px;
        padding-top: 15px;
        padding-bottom: 15px;
        &:hover {
          color: #9e0000;
          cursor: pointer;
        }
      }

      .case-tile-info {
        padding-top: 15px;
        padding-bottom: 15px;

        div {
          padding-left: 0;
          padding-right: 0;
        }
      }
    }
    .case-tile-button-col {
      .case-tile-button {
        border-radius: 0;
        border: solid #e4dfcb 1px;
        background-color: transparent;
        padding-top: 0;
        padding-bottom: 0;
        padding-right: 0;
        width: 210px;
        background-size: 25px;
        background-repeat: no-repeat;
        background-position-y: center;
        background-position-x: 10px;
        margin-bottom: 15px;
        margin-right: 15px;
        box-shadow: none;
        &.read {
          background-image: url("~assets/svg/read.svg");
        }
        &.copy {
          background-image: url("~assets/svg/copy.svg");
        }
        &.ask {
          background-image: url("~assets/svg/ask.svg");
        }
        div {
          background-color: #e4dfcb;
          margin-left: 30px;
          color: #474334;
          font-size: 15px;
          padding-top: 10px;
          padding-bottom: 10px;

        }
        &:hover {
          border: solid #9e0000 1px;
          div {
            color: white;
            background-color: #9e0000;
          }
        }
      }
    }
  }
}

/* планшетная версия - 768 - 1023 px*/
@media (min-width: 768px) {
}

/* ПК версия -  от 1024 px*/
@media (min-width: 1024px) {
  .case-tile {
    padding-top: 0;
    border-top: none;
    padding-bottom: 15px;

    .case-tile-info-col {
      padding-left: 30px;
      .case-tile-title {
        padding-top: 0;
        padding-bottom: 30px;
        min-height: 120px;
        font-size: 15px;
        font-weight: bold;
      }

      .case-tile-info {
        padding-top: 15px;
        font-size: 15px;

      }
    }
    .case-tile-button-col {
      padding-right: 0;
      text-align: right;
      .case-tile-button {
        margin-right: 0;

      }
    }

  }}

</style>
