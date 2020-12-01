<template>
<div>
  <page-title :page-title-text="pageTitleText"></page-title>
  <b-container>
    <b-row class="breadcrumb-row">
      <bread-crumbs :bread-crumb-items="breadCrumbItems"></bread-crumbs>
    </b-row>
    <b-row class="main-content-row">
      <b-col cols="12" md="4" class="rubric-col">
        <b-row class="rubric-title">Рубрики</b-row>

        <b-button v-b-modal.modalPopover class="rubric-select-button">{{selectedRubric}}</b-button>

        <b-modal id="modalPopover"  hide-footer>
          <template #modal-header="{ close }">
            <!-- Emulate built in modal header close button action -->
            <div class="modal-header-title">
              Выберите рубрику
            </div>
            <b-col class="modal-header-btn-block">
              <b-button @click="close()" class="modal-close-button">
              </b-button>
            </b-col>
          </template>
          <b-list-group class="rubric-list-group">
            <b-list-group-item
              v-for="listItem in rubricList"
              @click="selectedRubric = listItem.text; $bvModal.hide('modalPopover')"
              class="rubric-list-item"
            >
              {{listItem.text}}
            </b-list-group-item>
          </b-list-group>

        </b-modal>

      </b-col>
      <b-col cols="12" md="8" class="funds-col">
        <search-tile />
        <b-row class="items-info-row">
          <b-col cols="12" md="6" class="items-all">Всего фондов: 1-20 из 2905</b-col>
          <b-col cols="12" md="3" class="select-col">Выводить по:
          <select-form :options="perPageSelectList" :selected="20" />
          </b-col>
          <b-col cols="12" md="3" class="select-col">Сортировать:
          <select-form :options="sortSelectList" :selected="'По умолчанию'" />
          </b-col>
        </b-row>

      </b-col>
    </b-row>

  </b-container>
</div>
</template>

<script>
import PageTitle from "@/components/PageTitle";
import BreadCrumbs from "@/components/BreadCrumbs";
import SearchTile from "@/components/SearchTile";
import SelectForm from "@/components/SelectForm";
export default {
  name: "funds",
  components: {SelectForm, SearchTile, BreadCrumbs, PageTitle},
  data() {
    return {
      pageTitleText: 'Путеводитель по фондам досоветского периода',
      breadCrumbItems: [
        {
          text: 'Главная',
          to: '/'
        },
        {
          text: 'Путеводители – Путеводитель по фондам досоветского периода',
          active: true
        }
      ],
      selectedRubric: 'ВСЕ РУБРИКИ',
      rubricList: [
        {text: 'ВСЕ РУБРИКИ', link: '#'},
        {text: 'Коллекции документов', link: '#'},
        {text: 'Фонды военных учреждений, воинских частей и соединений', link: '#'},
        {text: 'Фонды личного происхождения', link: '#'},
        {text: 'Фонды местных органов власти и управления Временного правительства', link: '#'},
        {text: 'Фонды местных органов государственной власти и управления', link: '#'},
        {text: 'Фонды органов и учреждений здравоохранения', link: '#'},
        {text: 'Фонды органов и учреждений народного просвещения, науки и культуры, типографий', link: '#'},
        {text: 'Фонды органов полиции, жандармерии, тюремных учреждений', link: '#'},
        {text: 'Фонды органов сословного, городского и земского самоуправления', link: '#'},
        {text: 'Фонды органов суда, прокуратуры, нотариальных учреждений', link: '#'},
        {text: 'Фонды органов управления государственными имуществами, учреждений межевания и землеустройства, сельского, лесного хозяйства и продовольствия', link: '#'},
        {text: 'Фонды органов управления промышленностью, промышленных предприятий, учреждений строительства, транспорта и связи', link: '#'},
        {text: 'Фонды органов, учреждений и организаций духовного ведомства', link: '#'},
        {text: 'Фонды учреждений общественного призрения и общественных организаций', link: '#'}
      ],
      perPageSelectList: [20, 50, 100],
      sortSelectList: ['По умолчанию','По алфавиту','Сначала новые']

    }
  }
}
</script>

<style lang="scss">
/* по умолчанию -  мобильная версия - 0 - 767 px*/
@media (min-width: 0) {
  .main-content-row {
    .rubric-col {

      .rubric-title {
        font-size: 30px;
        font-family: 'Oswald', sans-serif;
        color: rgb(71, 68, 53);
        font-weight: bold;
        text-transform: uppercase;
        line-height: 1.2;
        text-align: left;
        background: url("~assets/svg/decor 1.svg") left no-repeat;
        background-size: 86px;
        padding-top: 20px;
        padding-bottom: 15px;
        padding-left: 20px;
        margin-left: -20px;
      }

      .rubric-select-button, .rubric-select-button:hover, .rubric-select-button:active, .rubric-select-button:focus {
        width: 100%;
        box-shadow: none;
        border-radius: 0;
        border: solid #e4dfcb 1px;
        color: #474334;
        text-align: left;
        font-family: 'Roboto', sans-serif;
        font-weight: bold;
        font-size: 14px;
        background: transparent url("~assets/svg/arrow down.svg") no-repeat;
        background-size: 5%;
        background-position-x: 95%;
        background-position-y: center;
        padding-right: 30px;
        margin-bottom: 15px;
        &.active {
          box-shadow: none;
        }


      }

    }
    .funds-col {
      padding-left: 0;
      padding-right: 0;
      .items-info-row {
        font-size: 14px;
        color: #474435;
        font-style: italic;
        line-height: 1.2;
        .items-all {
          margin-top: 10px;
        }
        .select-col {
          display: block;
          margin-top: 10px;
        }

      }
    }
  }
  .modal-content {
    .modal-header {
      .modal-header-title {
        width: 90%;
        font-size: 16px;
        font-weight: bold;
      }

      .modal-header-btn-block {
        padding-left: 0;
        padding-right: 0;
        display: flex;
        height: 100%;
        align-items: center;
        .modal-close-button, .modal-close-button:hover, .modal-close-button:active, .modal-close-button:focus  {
          box-shadow: none;
          border-radius: 0;
          border: none;
          background: transparent url("~assets/svg/cross small.svg") no-repeat;
          padding-right: 0;
          margin-left: auto;
          margin-top: auto;
          margin-bottom: auto;
        }
      }
    }
    .modal-body {
      .rubric-list-group {
        overflow: scroll;
        height: 600px;

        .rubric-list-item {
          border: none;
          border-radius: 0;
          font-size: 14px;
          line-height: 1.2;
          padding: 10px 0;
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

}
</style>
