<template>
<div>
  <page-title-inner :page-title-text="pageTitleText" :page-title-link="pageTitleLink"></page-title-inner>
  <b-container>
    <b-row class="breadcrumb-row">
      <bread-crumbs :bread-crumb-items="breadCrumbItems" />
    </b-row>
    <b-row class="main-content-row">
      <b-col cols="12" md="12" xl="3" class="case-path-col">
        <b-row class="case-path">
          <p><b-link :to="caseItem.inventory.fundType.link"><b>{{caseItem.inventory.fundType.text}}</b></b-link></p>
          <p><b-link :to="caseItem.inventory.invFund.link">{{caseItem.inventory.invFund.text}}</b-link></p>
          <p style="margin-left: 15px"><b-link :to="caseItem.inventory.invCode.link">{{caseItem.inventory.invCode.text}}</b-link></p>
          <p style="margin-left: 30px; padding-left: 15px; border-left: solid #efeada 1px;"><b-link :to="caseItem.title">{{caseItem.title}}</b-link></p>
        </b-row>
      </b-col>
      <b-col cols="12" md="12" xl="9" class="case-attributes-col">
        <b-row class="case-attributes-row">
          <b-col cols="12" xl="9">
            <b-row class="case-attributes">
              <b-row class="attribute-col-title">сведения</b-row>
              <p><b>{{caseItem.inventory.title + ': '}}</b><b-link :to="caseItem.inventory.invCode.link">{{caseItem.inventory.invCode.text}}</b-link></p>
              <p><b>{{caseItem.rubrics.title + ': '}}</b><b-link v-for="rubricItem in caseItem.rubrics.rubItems" :to="rubricItem.link">{{rubricItem.text}}</b-link></p>
              <p><b>{{caseItem.invSection.title + ': '}}</b><b-link :to="caseItem.invSection.link">{{caseItem.invSection.text}}</b-link></p>
              <p><b>{{caseItem.docType.title + ': '}}</b><b-link :to="caseItem.docType.link">{{caseItem.docType.text}}</b-link></p>
              <p><b>{{caseItem.pageAll.title + ': '}}</b>{{caseItem.pageAll.text}}</p>
              <p><b>{{caseItem.edgeDate.title + ': '}}</b>{{caseItem.edgeDate.text}}</p>
              <p><b>{{caseItem.street.title + ': '}}</b><b-link :to="caseItem.street.link">{{caseItem.street.text}}</b-link></p>
              <p><b>{{caseItem.fullScan.title + ': '}}</b>{{caseItem.fullScan.text}}</p>
              <p><b>{{caseItem.accessDoc.title + ': '}}</b>{{caseItem.accessDoc.text}}</p>
              <b-row class="case-persons-row">
                <b-row class="attribute-col-title">{{caseItem.persons.title}}</b-row>
                <b-row>
                  <b-link v-for="person in caseItem.persons.personItem" :to="person.link">{{person.text + ",&nbsp"}}</b-link>
                </b-row>
              </b-row>

            </b-row>
            <b-row class="case-annotation">
              <b-row class="attribute-col-title">{{ caseItem.annotation.title }}</b-row>
              <b-row class="attribute-col-body text" :class="showFullAnnClass">
                <p>{{caseItem.annotation.text}}</p>
              </b-row>
              <b-row class="attribute-col-show-full" :class="showFullAnnClass">
                <b-link @click="showFullSwitch('A')" >{{showFullLinkAnnText}}</b-link>
              </b-row>
            </b-row>
          </b-col>
          <b-col cols="12" xl="3" class="case-tile-button-col">
            <b-button class="case-tile-button read"><div>Читать дело</div></b-button>
            <b-button class="case-tile-button copy"><div>Заказать копию</div></b-button>
            <b-button class="case-tile-button ask"><div>Подать требование</div></b-button>
          </b-col>
        </b-row>
        <b-row class="linked-info-row">
          <b-row class="attribute-col-title">связанная информация</b-row>
          <b-row class="items-info-row">
            <b-col cols="12" md="6" class="items-all">Всего документов: 1-10 из 31</b-col>
            <b-col cols="12" md="6" class="select-col">Выводить по:
              <select-form
                :options="perPageSelectList"
                :selected="10"
                v-on:selectChanged="perPageSelectChanged"/>
            </b-col>
          </b-row>
          <b-row class="pagination-row">
            <pagination
              :total-rows="addListRows"
              :pagination-area-controls="paginationAreaControls"
              :per-page="perPage"
              />
          </b-row>
          <b-row class="linked-info">
            <b-col
              cols="12"
              class="linked-info-col"
              xl="6"
              v-for="addInfoItem in caseItem.addInfo"
            >
              <b-row class="add-item-code">{{addInfoItem.code}}</b-row>
              <b-row class="add-item-text">
                <b-link :to="addInfoItem.link">{{addInfoItem.text}}</b-link>
                <b-img src="~assets/img/folder.png"></b-img>
              </b-row>
            </b-col>
          </b-row>
          <b-row class="pagination-row">
            <pagination
              :total-rows="addListRows"
              :pagination-area-controls="paginationAreaControls"
              :per-page="perPage"
            />
          </b-row>

        </b-row>

      </b-col>

    </b-row>


  </b-container>
  <join-us />
</div>
</template>

<script>
import PageTitleInner from "@/components/PageTitleInner";
import BreadCrumbs from "@/components/BreadCrumbs";
import Pagination from "@/components/Pagination";
import JoinUs from "@/components/JoinUs";
import SelectForm from "@/components/SelectForm";

export default {
  name: "caseType",
  components: {SelectForm, JoinUs, Pagination, BreadCrumbs, PageTitleInner},
  data() {
    return {
      pageTitleText: 'Циркуляры и приказы ВСНХ СССР, распоряжения  Центрального Управления лесной промышленности',
      pageTitleLink: {text: 'Назад на страницу описи', link: 'inventory'},
      showFullAnn: false,
      showFullAnnClass: '',
      showFullLinkAnnText: 'Показать полный текст',
      paginationAreaControls: '',
      perPage: 10,
      perPageSelectList: [10, 20],
      breadCrumbItems: [
        {
          text: 'Главная',
          to: '/'
        },
        {
          text: 'Путеводители – Путеводитель по фондам досоветского периода',
          to: 'funds'
        },
        {
          text: 'Ф. Р-91 Оп. 3',
          to: 'inventory'
        },
        {
          text: 'Циркуляры и приказы ВСНХ СССР, распоряжения  Центрального Управления лесной промышленности',
          active: true
        }
      ],
      caseItem: {
        title: 'Циркуляры и приказы ВСНХ СССР, распоряжения  Центрального Управления лесной промышленности',
        inventory: {
          title: 'Опись',
          invCode: {text: 'Ф. Р-155 Оп. 1', link: ''},
          invFund: {
            text: 'Ф. Р-155 Земельное управление Ульяновского губернского исполнительного комитета Совета рабочих, крестьянских и красноармейских депутатов. г. Ульяновск (февраль 1918 г. 22.07.1929 г.)',
            link: ''
          },
          fundType: {text: 'Фонды советского периода', link: ''},
        },
        rubrics: {
          title: 'Рубрики',
          rubItems: [
            {text: 'рубрика 1, ', link: ''},
            {text: 'рубрика 2, ', link: ''},
            {text: 'рубрика 3', link: ''}
          ]
        },
        invSection: {title: 'Раздел описи', text: 'Административный отдел', link: ''},
        categoryDoc: {title: 'Категория дела', text: 'ОЦД', link: ''},
        docType: {title: 'Вид документов', text: 'Управленческая документация', link: ''},
        pageAll: {title: 'Количество листов', text: '88', link: ''},
        edgeDate: {title: 'Хронологические рамки', text: '04.05.1904- 20.01.1906', link: ''},
        street: {title: 'Населенный пункт', text: 'Седлецкая губ. - Царство Польское', link: ''},
        fullScan: {title: 'Статус сканирования', text: 'Дело не отсканировано', link: ''},
        accessDoc: {title: 'Доступ', text: 'откр', link: ''},
        persons: {
          title: 'Персоны',
          personItem: [
            {text: 'Арсеньев Василий Сергеевич', link: ''},
            {text: 'Арсеньев Дмитрий Васильевич', link: ''},
            {text: 'Арсеньев Михаил Михайлович', link: ''},
            {text: 'Арсеньевы', link: ''},
            {text: 'Боровиковский Владимир Лукич', link: ''},
            {text: 'Давыдовы', link: ''},
            {text: 'Екатерина II', link: ''}
          ]
        },
        annotation: {
          title: 'Аннотация',
          text: 'Постановления и циркуляры губисполкома. Протоколы заседаний губземотдела, губернских и уездных земельных съездов, губернских и уездных земельных коллегий, волостных земельных отделов, комитетов посевных площадей. План восстановления сельского хозяйства черноземной части Ульяновской губернии на 1925 -1930 гг. Отчеты и доклады о работе губернского, уездных и районных земельных отделов. Постановления и циркуляры губисполкома. Протоколы заседаний губземотдела, губернских и уездных земельных съездов, губернских и уездных земельных коллегий, волостных земельных отделов, комитетов посевных площадей. План восстановления сельского хозяйства черноземной части Ульяновской губернии на 1925 -1930 гг. Отчеты и доклады о работе губернского, уездных и районных земельных отделов.' +
            'Постановления и циркуляры губисполкома. Протоколы заседаний губземотдела, губернских и уездных земельных съездов, губернских и уездных земельных коллегий, волостных земельных отделов, комитетов посевных площадей. План восстановления сельского хозяйства черноземной части Ульяновской губернии на 1925 -1930 гг. Отчеты и доклады о работе губернского, уездных и районных земельных отделов.'
        },
        addInfo: [
          {code: 'Ф. Р-1861 Оп. 1 Д. 1 Лл. 67', text: 'Основные положения закона о земле', link: ''},
          {
            code: 'Ф. Р-1861 Оп. 1 Д. 1 Лл. 124',
            text: 'Об участии в работе общественных и государственных учреждений членов партии социалистов-революционеров. Инструкция Центрального комитета партии эсеров',
            link: ''
          },
          {
            code: 'Ф. Р-1861 Оп. 1 Д. 1 Лл. 124',
            text: 'Об участии в работе общественных и государственных учреждений членов партии социалистов-революционеров. Инструкция Центрального комитета партии эсеров',
            link: ''
          },
          {
            code: 'Ф. Р-1861 Оп. 1 Д. 1 Лл. 124',
            text: 'Об участии в работе общественных и государственных учреждений членов партии социалистов-революционеров. Инструкция Центрального комитета партии эсеров',
            link: ''
          },
          {
            code: 'Ф. Р-1861 Оп. 1 Д. 1 Лл. 124',
            text: 'Об участии в работе общественных и государственных учреждений членов партии социалистов-революционеров. Инструкция Центрального комитета партии эсеров',
            link: ''
          },
          {
            code: 'Ф. Р-1861 Оп. 1 Д. 1 Лл. 144',
            text: 'Об отношении партии эсеров к 1-й мировой войне. Резолюция к III съезду партии эсеров',
            link: ''
          },
          {
            code: 'Ф. Р-1861 Оп. 1 Д. 1 Лл. 144',
            text: 'Об отношении партии эсеров к 1-й мировой войне. Резолюция к III съезду партии эсеров',
            link: ''
          },
          {
            code: 'Ф. Р-1861 Оп. 1 Д. 1 Лл. 144',
            text: 'Об отношении партии эсеров к 1-й мировой войне. Резолюция к III съезду партии эсеров',
            link: ''
          },
          {
            code: 'Ф. Р-1861 Оп. 1 Д. 1 Лл. 144',
            text: 'Об отношении партии эсеров к 1-й мировой войне. Резолюция к III съезду партии эсеров',
            link: ''
          },
          {
            code: 'Ф. Р-1861 Оп. 1 Д. 1 Лл. 144',
            text: 'Об отношении партии эсеров к 1-й мировой войне. Резолюция к III съезду партии эсеров',
            link: ''
          },
        ]

      }
    }
  },
  methods: {
    showFullSwitch: function (label) {
      switch (label) {
        case 'A':
          if (this.showFullAnn == false) {
            this.showFullAnn = true;
            this.showFullAnnClass = 'show-full';
            this.showFullLinkAnnText = 'Скрыть полный текст';
          } else {
            this.showFullAnn = false;
            this.showFullAnnClass = '';
            this.showFullLinkAnnText = 'Показать полный текст';
          }
          break;
      }
    },
    perPageSelectChanged: function (selected){
      this.perPage= selected;
    }
  },
  computed: {
    addListRows() {
      return this.caseItem.addInfo.length
    }
  }
}
</script>

<style lang="scss">
/* по умолчанию -  мобильная версия - 0 - 767 px*/
@media (min-width: 0) {
  .main-content-row {
    margin-bottom: 45px !important;
    .case-path-col {
      .case-path {

      }
    }
    .case-attributes-col {
      .case-attributes-row {
        .case-attributes {
          flex-direction: column;
          border: solid #efeada 1px;
          padding: 15px;
          .attribute-col-title {
            text-transform: uppercase;
            font-weight: bold;
            font-size: 16px;
            margin-bottom: 15px;
          }
          .case-persons-row {
            border-top: solid #efeada 1px;
            padding-top: 30px;
            .attribute-col-title {
              text-transform: uppercase;
              font-weight: bold;
              font-size: 16px;
              margin-bottom: 15px;
            }
          }
        }
        .case-annotation {
          margin-top: 30px;
          .attribute-col-title {
            text-transform: uppercase;
            font-weight: bold;
            font-size: 16px;
            margin-bottom: 15px;
          }
          .attribute-col-body {
            flex-direction: column;
            font-size: 16px;
            max-height: 190px;
            overflow: hidden;
            text-align: justify;

            a {
              text-decoration: underline;
            }
            &.text {
              max-height: 190px;
            }
            &.show-full {
              max-height: none;
              height: auto;
            }
          }
          .attribute-col-show-full {
            background-image: url("~assets/svg/arrow down d.svg");
            background-repeat: no-repeat;
            background-position: right;
            background-size: 10px;
            display: flex;
            padding-right: 15px;
            width: 100%;
            margin-top: 15px;
            a {
              margin-left: auto;
              font-size: 16px;
              font-weight: bold;
              text-decoration: none;
              border-bottom: dashed #474334 1px;
              &:hover {
                color: #9e0000;
                border-bottom: dashed #9e0000 1px;

              }
            }
            &.show-full {
              background-image: url("~assets/svg/arrow up d.svg");
              a {
                &:hover {
                  color: #5e759f;
                  border-bottom: dashed #5e759f 1px;
                }
              }
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
      .linked-info-row {
        margin-top: 45px;
        margin-left: 15px;
        flex-direction: column;
        .attribute-col-title {
          text-transform: uppercase;
          font-weight: bold;
          font-size: 16px;
          margin-bottom: 15px;
        }
        .items-info-row {
          font-size: 14px;
          color: #474435;
          font-style: italic;
          line-height: 1.2;
          margin-bottom: 20px;
          .items-all {
            margin-top: 10px;
            padding-left: 0;
          }
          .select-col {
            display: block;
            margin-top: 10px;
            text-align: right;
          }

        }
        .linked-info {
          margin-top: 45px;
          .linked-info-col {
            margin-bottom: 60px;
            padding-right: 30px;
            .add-item-code {
              font-size: 14px;
              color: #949182;
              width: 100%;
              margin-bottom: 30px;
            }
            .add-item-text {
              font-size: 14px;
              font-weight: bold;
              width: 100%;
              display: block;

            }
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
  .main-content-row {
    .case-path-col {
      border-right: solid #474435 1px;
      padding-right: 30px;
      .case-path {

      }
    }
    .case-attributes-col {
      .case-attributes-row {
        .case-attributes {
          padding: 30px;
          .attribute-col-title {
            font-size: 16px;
          }
        }
        .case-tile-button-col {
          padding-right: 0;
          text-align: right;
          .case-tile-button {
            margin-right: 0;
          }
        }
      }
    }
  }
}
</style>
