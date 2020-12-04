<template>
<div>
  <page-title-inner :page-title-text="pageTitleText" :page-title-link="pageTitleLink" />
  <b-container>
    <b-row class="breadcrumb-row">
      <bread-crumbs :bread-crumb-items="breadCrumbItems"></bread-crumbs>
    </b-row>
    <b-row class="attributes-row">
      <b-col cols="12" md="6" class="attribute-col">
        <b-row class="attribute-col-title">сведения</b-row>
        <b-row class="attribute-col-body" style="text-align: left">
          <p><b>{{stock.archive.title + ': '}}</b><b-link :to="stock.archive.link">{{stock.archive.text}}</b-link></p>
          <p><b>{{stock.numb.title + ': '}}</b>{{stock.numb.text}}</p>
          <p><b>{{stock.name.title + ': '}}</b>{{stock.name.text}}</p>
          <p><b>{{stock.stockType.title + ': '}}</b><b-link :to="stock.stockType.link">{{stock.stockType.text}}</b-link></p>
          <p><b>{{stock.hPeriods.title + ': '}}</b><b-link :to="stock.hPeriods.link">{{stock.hPeriods.text}}</b-link></p>
          <p><b>{{stock.categoryFond.title + ': '}}</b>{{stock.categoryFond.text}}</p>
          <p><b>{{stock.typeFond.title + ': '}}</b><b-link :to="stock.typeFond.link">{{stock.typeFond.text}}</b-link></p>
          <p><b>{{stock.accessDoc.title + ': '}}</b><b-link :to="stock.accessDoc.link">{{stock.accessDoc.text}}</b-link></p>
        </b-row>
      </b-col>
      <b-col cols="12" md="6" class="attribute-col">
        <b-row class="attribute-col-title">переименования</b-row>
        <b-row class="attribute-col-body" :class="showFullRenamesClass" style="text-align: left">
          <div v-for="renameItem in stock.renames">
            <p><b>{{renameItem.renameDate.title + ': '}}</b>{{renameItem.renameDate.text}}</p>
            <p><b>{{renameItem.renaming.title + ': '}}</b>{{renameItem.renaming.text}}</p>
            <p><b>{{renameItem.shortRename.title + ': '}}</b>{{renameItem.shortRename.text}}</p>
          </div>
        </b-row>
        <b-row class="attribute-col-show-full" :class="showFullRenamesClass">
          <b-link @click="showFullSwitch('R')" >{{showFullLinkRenamesText}}</b-link>
        </b-row>
      </b-col>
      <b-col cols="12" md="6" class="attribute-col">
        <b-row class="attribute-col-title">{{stock.annotation.title}}</b-row>
        <b-row class="attribute-col-body text" :class="showFullAnnClass">
            <p>{{stock.annotation.text}}</p>
        </b-row>
        <b-row class="attribute-col-show-full" :class="showFullAnnClass">
          <b-link @click="showFullSwitch('A')" >{{showFullLinkAnnText}}</b-link>
        </b-row>
      </b-col>
      <b-col cols="12" md="6" class="attribute-col">
        <b-row class="attribute-col-title">{{stock.histInfo.title}}</b-row>
        <b-row class="attribute-col-body text" :class="showFullHistClass">
          <p>{{stock.histInfo.text}}</p>
        </b-row>
        <b-row class="attribute-col-show-full" :class="showFullHistClass">
          <b-link @click="showFullSwitch('H')" >{{showFullLinkHistText}}</b-link>
        </b-row>
      </b-col>
    </b-row>
    <b-row class="tree-row">
      <b-col cols="12" md="3" class="tree-select-col">
        <b-row>
          <attr-tree :options="fundTreeOptions"></attr-tree>
        </b-row>
        <b-row></b-row>
      </b-col>
      <b-col cols="12" md="9" class="cases-list-col">
        <search-tile :search-tile-title="searchTileTitle" />
        <b-row class="select-tile-row">
          <div class="select-tile" v-for="selectTile in selectTiles">
            <div class="select-text" :to="selectTile.link">
              {{selectTile.text}}
            </div>
            <b-button class="select-close-button"></b-button>
          </div>
        </b-row>
        <b-row class="items-info-row">
          <b-col cols="12" md="6" class="items-all">Всего дел: 1-10 из 2905</b-col>
          <b-col cols="12" md="6" class="select-col">Выводить по:
            <select-form
              :options="perPageSelectList"
              :selected="10"
              v-on:selectChanged="perPageSelectChanged"
            />
          </b-col>
        </b-row>
        <b-row class="pagination-row">
          <pagination

            :total-rows="casesListRows"
            :pagination-area-controls="paginationAreaControls"
            :per-page="perPage" />
        </b-row>
        <b-row class="cases-list-row">
          <b-row class="case-tile" v-for="caseItem in casesList">
            <b-col cols="12" md="12" xl="9" class="case-tile-info-col">
              <b-row class="case-tile-title">
                <b-link :to="caseItem.link">{{caseItem.code}}
                  <b-img src="~assets/img/folder.png"></b-img>
                </b-link>
              </b-row>
              <b-row class="case-tile-info">
                <b-col cols="12" md="4">{{'Номер дела: '+ caseItem.number}} </b-col>
                <b-col cols="12" md="8">{{caseItem.scanned}}</b-col>
              </b-row>
            </b-col>
            <b-col cols="12" md="12" xl="3" class="case-tile-button-col">
              <b-button class="case-tile-button read"><div>Читать дело</div></b-button>
              <b-button class="case-tile-button copy"><div>Заказать копию</div></b-button>
              <b-button class="case-tile-button ask"><div>Подать требование</div></b-button>
            </b-col>

          </b-row>

        </b-row>
        <b-row class="pagination-row">
          <pagination

            :total-rows="casesListRows"
            :pagination-area-controls="paginationAreaControls"
            :per-page="perPage" />
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
import AttrTree from "@/components/AttrTree";
import SearchTile from "@/components/SearchTile";
import Pagination from "@/components/Pagination";
import JoinUs from "@/components/JoinUs";
export default {
  name: "fundsType",
  components: {JoinUs, Pagination, SearchTile, AttrTree, BreadCrumbs, PageTitleInner},
  data() {
    return {
      pageTitleText: '1917-1921гг. Симбирская контора закупочно-распределительного пункта Всероссийского центрального союза потребительских обществ  г.Симбирск Симбирской губернии',
      pageTitleLink: {text:'Назад к путеводителю по фондам', link: 'funds'},
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
          text: '1917-1921гг. Симбирская контора закупочно-распределительного пункта Всероссийского центрального союза потребительских обществ  г.Симбирск Симбирской губернии',
          active: true
        }
      ],
      searchTileTitle: 'Поиск по делам фонда',
      showFullRenames: false,
      showFullRenamesClass: '',
      showFullLinkRenamesText: 'Показать полный текст',
      showFullAnn: false,
      showFullAnnClass: '',
      showFullLinkAnnText: 'Показать полный текст',
      showFullHist: false,
      showFullHistClass: '',
      showFullLinkHistText: 'Показать полный текст',
      stock: {
        archive: {title: 'Архив', text: 'Государственный архив Ульяновской области', link: ''},
        numb: {title: 'Номер фонда', text: 'Р-1'},
        name: {title: 'Наменование фонда', text: 'Симбирская контора закупочно-распределительного пункта'},
        stockType: {title: 'Вид фонда', text: 'фонд учреждения, организации', link: ''},
        hPeriods: {title: 'Исторический период', text: 'послереволюционный', link: ''},
        categoryFond: {title: 'Категория фонда', text: '3'},
        typeFond: {title: 'Тип фонда', text: 'Управленческая документация', link: ''},
        accessDoc: {title: 'Доступ', text: 'откр', link: ''},
        renames: [
          {
            renameDate: {title: 'Дата', text: '28.02.1918 (неточно)-31.01.1922 (неточно)'},
            renaming: {title: 'Наименование', text: 'Фонд Р-155. Земельный отдел Ульяновского губернского исполнительного комитета Совета рабочих, солдатских и крестьянских ( с апреля 1918 г. - рабочих и крестьянских, с ноября 1918 г. - рабочих, крестьянских и красноармейских ) депутатов г. Ульяновск'},
            shortRename: {title: 'Сокращенное наименование', text: 'Земельный отдел Ульяновского губисполкома '}
          },
          {
            renameDate: {title: 'Дата', text: '28.02.1918 (неточно)-31.01.1922 (неточно)'},
            renaming: {title: 'Наименование', text: 'Фонд Р-155. Земельный отдел Ульяновского губернского исполнительного комитета Совета рабочих, солдатских и крестьянских ( с апреля 1918 г. - рабочих и крестьянских, с ноября 1918 г. - рабочих, крестьянских и красноармейских ) депутатов г. Ульяновск'},
            shortRename: {title: 'Сокращенное наименование', text: 'Земельный отдел Ульяновского губисполкома '}
          },
          {
            renameDate: {title: 'Дата', text: '28.02.1918 (неточно)-31.01.1922 (неточно)'},
            renaming: {title: 'Наименование', text: 'Фонд Р-155. Земельный отдел Ульяновского губернского исполнительного комитета Совета рабочих, солдатских и крестьянских ( с апреля 1918 г. - рабочих и крестьянских, с ноября 1918 г. - рабочих, крестьянских и красноармейских ) депутатов г. Ульяновск'},
            shortRename: {title: 'Сокращенное наименование', text: 'Земельный отдел Ульяновского губисполкома '}
          }
        ],
        annotation: {title: 'Аннотация', text: 'Протоколы совещаний общественно кооперативных организаций г. Симбирска, дела служащих, постановления и приказы о мобилизации граждан, протоколы тарифно-расценочной комиссии, книги для записей договоров, списки служащих, переписки, документы по страхованию товаров, ведомости о движении хлебопродуктов на ссыпных пунктах, ведомости о движении морепродуктов на ссыпных пунктах.'},
        histInfo: {title: 'Историческая справка', text: 'В феврале 1918 года постановлением Ульяновского губисполкома был создан земельный отдел. (ф.Р-155, оп.1, д.2, л.70 ). Ведал землеустройством, организацией государственных земельных имуществ, руководил сельскохозяйственными трестами, ветеринарными учреждениями и лесным хозяйством губернии. В январе 1922 года приказом губисполкома переименован в земельное управление ( газета "Коммунар", 15 января 1922 ...'}
      },
      fundTreeOptions: [
        {
        id: 'a',
        label: 'a',
        children: [ {
          id: 'aa',
          label: 'aa',
          }, {
          id: 'ab',
          label: 'ab',
          } ],
        }, {
        id: 'b',
        label: 'b',
        }, {
        id: 'c',
        label: 'c',
      } ],
      selectTiles: [
        {text: 'Ф. Р-155 Оп. 1', value: ''},
        {text: '1927', value: ''},
        {text: 'Бухгалтерия', value: ''}
      ],
      perPage: 10,
      paginationAreaControls: '',
      perPageSelectList: [10, 20],
      casesList: [
        {number: '1', scanned: 'Дело не отсканировано', link:'caseType', code: 'Ф. Р-91 Оп. 3 Д. 1 Циркуляры и приказы ВСНХ СССР, распоряжения Центрального Управления лесной промышленности'},
        {number: '2', scanned: 'Дело отсканировано', link:'#', code: 'Ф. Р-91 Оп. 3 Д. 2 Циркулярное письмо Симбирского Городского районного комитета РКП(б) о недопустимости бойкотирования в приёме на работу членов партии'},
        {number: '3', scanned: 'Дело отсканировано не полностью', link:'#', code: 'Ф. Р-91 Оп. 3 Д. 3 Приказы ВСНХ СССР, Центрального Управления лесной промышленности'},
        {number: '5', scanned: 'Дело отсканировано', link:'#', code: 'Ф. Р-91 Оп. 3 Д. 5 Директивное указание Симбирского губисполкома от 20 ноября 1923 года об особо осторожной выдаче сведений иностранцам, занимающимся коммерческой деятельностью и переписка с административным отделом управления губисполкома о борьбе с преступностью'},
        {number: '6', scanned: 'Дело не отсканировано', link:'#', code: 'Ф. Р-91 Оп. 3 Д. 6 Циркуляры Симбирского губернского объединения лесной промышленности «Симбирсклес» о заключении коллективного договора с губернским Союзом деревообделочников'},
        {number: '7', scanned: 'Дело отсканировано не полностью', link:'#', code: 'Ф. Р-91 Оп. 3 Д. 7 Переписка с Симбирским губисполкомом и губсовнархозом о сокращении штатного расписания и по личному составу'},
        {number: '8', scanned: 'Дело отсканировано', link:'#', code: 'Ф. Р-91 Оп. 3 Д. 8 Статсведения о личном составе управления «Симбирсклеса», их партийной принадлежности и социальном происхождении на 15 ноября 1923 года, переписка с предприятиями по кадровым вопросам'},
        {number: '9', scanned: 'Дело не отсканировано', link:'#', code: 'Ф. Р-91 Оп. 3 Д. 9 Список служащих объединения «Симбирсклес» с указанием их социального происхождения и судимости, переписка с ОГПУ об отправке почты через фельдкорпус'},
        {number: '10', scanned: 'Дело отсканировано', link:'#', code: 'Ф. Р-91 Оп. 3 Д. 10 Переписка с Симбирским губпрокурором о расследовании злоупотреблений на Мелекесском лесозаводе'},
        {number: '11', scanned: 'Дело отсканировано не полностью', link:'#', code: 'Ф. Р-91 Оп. 3 Д. 11 Список членов комсомола, работающих на Инзенском лесопильном заводе и переписка с ним по личному составу'}
      ]
    }
  },
  methods: {
    showFullSwitch: function (label) {
      switch (label) {
        case 'R':
          if (this.showFullRenames == false) {
            this.showFullRenames = true;
            this.showFullRenamesClass = 'show-full';
            this.showFullLinkRenamesText = 'Скрыть полный текст';
          } else {
            this.showFullRenames = false;
            this.showFullRenamesClass = '' ;
            this.showFullLinkRenamesText = 'Показать полный текст';
          }
          break;
        case 'A':
          if (this.showFullAnn == false) {
            this.showFullAnn = true;
            this.showFullAnnClass = 'show-full';
            this.showFullLinkAnnText = 'Скрыть полный текст';
          } else {
            this.showFullAnn = false;
            this.showFullAnnClass = '' ;
            this.showFullLinkAnnText = 'Показать полный текст';
          }
          break;
        case 'H':
          if (this.showFullHist == false) {
            this.showFullHist = true;
            this.showFullHistClass = 'show-full';
            this.showFullLinkHistText = 'Скрыть полный текст';
          } else {
            this.showFullHist = false;
            this.showFullHistClass = '' ;
            this.showFullLinkHistText = 'Показать полный текст';
          }
          break;
      }


    },
    perPageSelectChanged: function (selected){
      this.perPage= selected;
    }
  },
  computed: {
    casesListRows() {
      return this.casesList.length
    }
  },
}
</script>

<style lang="scss">
/* по умолчанию -  мобильная версия - 0 - 767 px*/
@media (min-width: 0) {
  .attributes-row {
    .attribute-col {
      padding-bottom: 30px;
      .attribute-col-title {
        font-size: 15px;
        color: #474435;
        font-weight: bold;
        text-transform: uppercase;
        line-height: 1.733;
        margin-bottom: 20px;
      }
      .attribute-col-body {
        flex-direction: column;
        font-size: 15px;
        max-height: 400px;
        overflow: hidden;
        text-align: justify;
        a {
          text-decoration: underline;
        }
        &.text {
          max-height: 200px;
          height: 200px;
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
  }
  .tree-row {
    margin-bottom: 60px;
    .cases-list-col {
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
          .select-close-button {
            background-color: transparent;
            background-image: url("~assets/svg/cross.svg");
            background-size: 10px;
            background-position: center;
            background-repeat: no-repeat;
            border-radius: 0;
            border: none;
            margin-left: 10px;


          }
        }
      }
      .items-info-row {
        font-size: 14px;
        color: #474435;
        font-style: italic;
        line-height: 1.2;
        margin-bottom: 20px;
        .items-all {
          margin-top: 10px;
        }
        .select-col {
          display: block;
          margin-top: 10px;
        }

      }
      .pagination-row {
        border-top: solid #e4dfcb 1px;
        border-bottom: solid #e4dfcb 1px;
      }
      .cases-list-row {
        margin-bottom: 30px;
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
    }
  }
}
/* планшетная версия - 768 - 1023 px*/
@media (min-width: 768px) {
  .attributes-row {
    .attribute-col {
      padding-left: 30px;
      padding-right: 30px;

      .attribute-col-title {
      }

      .attribute-col-body {
      }
    }
  }
  .tree-row {
    .cases-list-col {
      .items-info-row {
        .items-all {
        }

        .select-col {

          text-align: right;

        }
      }
    }
  }
}

/* ПК версия -  от 1024 px*/
@media (min-width: 1024px) {
  .tree-row {
    .cases-list-col {
      .cases-list-row {
        border-top: solid #e4dfcb 1px;
        margin-top: 45px;
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

        }
      }
    }
  }
}

</style>
