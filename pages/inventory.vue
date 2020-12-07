<template>
<div>
  <page-title-inner :page-title-text="pageTitleText" :page-title-link="pageTitleLink"></page-title-inner>
  <b-container>
    <b-row class="breadcrumb-row">
      <bread-crumbs :bread-crumb-items="breadCrumbItems" />
    </b-row>
    <b-row class="attributes-row">
        <b-col cols="12" class="attribute-col-title">сведения</b-col>
        <b-col cols="12" md="6" class="attribute-col">
          <b-row class="attribute-col-body" style="text-align: left">
            <p><b>{{inventory.archive.title + ': '}}</b><b-link :to="inventory.archive.link">{{inventory.archive.text}}</b-link></p>
            <p><b>{{inventory.codee.title + ': '}}</b>{{inventory.codee.text}}</p>
            <p><b>{{inventory.fundNumRef.title + ': '}}</b>{{inventory.fundNumRef.text}}</p>
            <p><b>{{inventory.nameFond.title + ': '}}</b><b-link :to="inventory.nameFond.link">{{inventory.nameFond.text}}</b-link></p>
            <p><b>{{inventory.sources.title + ': '}}</b>{{inventory.sources.text}}</p>
            <p><b>{{inventory.reprMeans.title + ': '}}</b>{{inventory.reprMeans.text}}</p>
            <p><b>{{inventory.note.title + ': '}}</b>{{inventory.note.text}}</p>
            <p><b>{{inventory.storageLife.title + ': '}}</b>{{inventory.storageLife.text}}</p>
          </b-row>
        </b-col>
        <b-col cols="12" md="6" class="attribute-col">
        <b-row class="attribute-col-body" style="text-align: left">
          <p><b>{{inventory.baseRevenue.title + ': '}}</b>{{inventory.baseRevenue.text}}</p>
          <p><b>{{inventory.recordSource.title + ': '}}</b>{{inventory.recordSource.text}}</p>
          <p><b>{{inventory.sequenceNumb.title + ': '}}</b>{{inventory.sequenceNumb.text}}</p>
          <p><b>{{inventory.fNote.title + ': '}}</b>{{inventory.fNote.text}}</p>
          <p><b>{{inventory.motion.title + ': '}}</b>{{inventory.motion.text}}</p>
          <p><b>{{inventory.category.title + ': '}}</b>{{inventory.category.text}}</p>
          <p><b>{{inventory.viewDocument.title + ': '}}</b>{{inventory.viewDocument.text}}</p>
          <p><b>{{inventory.totalInvent.title + ': '}}</b>{{inventory.totalInvent.text}}</p>
          <p><b>{{inventory.museumObject.title + ': '}}</b>{{inventory.museumObject.text}}</p>
        </b-row>
        </b-col>
        <b-col cols="12" md="6" class="attribute-col annotation">
          <b-row class="attribute-col-title">{{inventory.annotation.title}}</b-row>
          <b-row class="attribute-col-body text" :class="showFullAnnClass">
            <p>{{inventory.annotation.text}}</p>
          </b-row>
          <b-row class="attribute-col-show-full" :class="showFullAnnClass">
            <b-link @click="showFullSwitch('A')" >{{showFullLinkAnnText}}</b-link>
          </b-row>
        </b-col>
        <b-col cols="12" md="6" class="attribute-col scan">
          <b-row class="attribute-col-title">Электронная копия</b-row>
          <b-row class="attribute-col-body" style="text-align: left">
            <b-col cols="2" class="image-col">
              <b-img class="scan-image" src="~assets/img/inv-img.png"></b-img>
            </b-col>
            <b-col cols="10" class="scan-text">
              <b-row class="scan-text-inner">
                <p>Опись дел постоянного хранения</p>
                <b-link to="">Скачать (81Кб)</b-link>
              </b-row>

            </b-col>
          </b-row>
        </b-col>
      </b-row>
    <b-row class="tree-row">
      <b-col cols="12" md="3" class="tree-select-col">
      </b-col>
      <b-col cols="12" md="9" class="cases-list-col">
        <search-tile :search-tile-title="searchTileTitle" />
        <select-tile-row :select-tiles="selectTiles" />
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
          :per-page="perPage"
          />
        </b-row>
        <b-row class="cases-list-row">
          <case-tile v-for="caseItem in casesList" :case-item="caseItem" />
        </b-row>
        <b-row class="pagination-row">
          <pagination
            :total-rows="casesListRows"
            :pagination-area-controls="paginationAreaControls"
            :per-page="perPage"
          />
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
import SearchTile from "@/components/SearchTile";
import SelectTileRow from "@/components/SelectTileRow";
import SelectForm from "@/components/SelectForm";
import Pagination from "@/components/Pagination";
import CaseTile from "@/components/CaseTile";
import JoinUs from "@/components/JoinUs";
export default {
  name: "inventory",
  components: {JoinUs, CaseTile, Pagination, SelectForm, SelectTileRow, SearchTile, BreadCrumbs, PageTitleInner},
  data() {
    return {
      pageTitleText: '1917-1921гг. Симбирская контора закупочно-распределительного пункта Всероссийского центрального союза потребительских обществ  г.Симбирск Симбирской губернии',
      pageTitleLink: {text: 'Назад к путеводителю по фондам', link: 'funds'},
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
      showFullAnn: false,
      showFullAnnClass: '',
      showFullLinkAnnText: 'Показать полный текст',
      inventory: {

        archive: {title: 'Архив', text: 'Государственный архив Ульяновской области', link: ''},
        codee: {title: 'Шифр', text: 'Ф. Р-1 Оп. 1', link: ''},
        fundNumRef: {title: 'Номер фонда', text: 'Р-1', link: ''},
        fundNum: {title: 'Фонд', text: 'Р-1', link: ''},
        nameFond: {title: 'Наименование фонда', text: 'Симбирская контора закупочно-распределительного пункта', link: ''},
        sources: {title: 'Источник поступления', text: 'государственная организация', link: ''},
        reprMeans: {title: 'Способ воспроизведения', text: 'рукописный', link: ''},
        note: {title: 'Примечание', text: 'Акт о технической ошибки в учётных документах от 15.05.2019 (-3 ед.хр)', link: ''},
        storageLife: {title: 'Срок хранения', text: 'постоянно', link: ''},
        baseRevenue: {title: 'Основание поступления', text: 'распоряжение АО', link: ''},
        recordSource: {title: 'Источник записи', text: 'ULKSS_DB.BAK от 19.08.2020', link: ''},
        sequenceNumb: {title: 'Цифровая копия - Порядковый номер', text: '1', link: ''},
        fNote: {title: 'Цифровая копия - Примечание', text: 'Советский период/Ф. 0001-0500/Ф.Р-001/Р-1_1', link: ''},
        motion: {title: 'Движение - В наличии', text: 'да', link: ''},
        category: {title: 'Категория описи', text: '3', link: ''},
        viewDocument: {title: 'Состав и объем документов - Вид документов', text: 'Документы на бумажной основе', link: ''},
        totalInvent: {title: 'Состав и объем документов - Всего ед. хранения', text: '136', link: ''},
        museumObject: {title: 'Наличие музейных предметов', text: 'нет', link: ''},
        annotation: {title: 'Аннотация', text: 'Протоколы совещаний общественно кооперативных организаций г. Симбирска, дела служащих, постановления и приказы о мобилизации граждан, протоколы тарифно-расценочной комиссии, книги для записей договоров, списки служащих, переписки, документы по страхованию товаров, ведомости о движении хлебопродуктов на ссыпных пунктах, ведомости о движении морепродуктов на ссыпных пунктах.'},



      },
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
    .attribute-col-title {
      font-size: 15px;
      color: #474435;
      font-weight: bold;
      text-transform: uppercase;
      line-height: 1.733;
      margin-bottom: 20px;
      padding-left: 30px;
    }

    .attribute-col {
      padding-bottom: 30px;
      padding-left: 30px;

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
          max-height: 180px;
        }

        &.show-full {
          max-height: none;
          height: auto;
        }

        .image-col {

          background-color: #f7f5ed;

          .scan-image {

          }
        }

        .scan-text {
          margin-top: auto;
          margin-bottom: auto;

          .scan-text-inner {
            flex-direction: column;

            a {
              border-bottom: dashed #474334 1px;
              font-weight: bold;
              text-decoration: none;
              width: fit-content;

              &:hover {
                border-bottom: dashed #9e0000 1px;
              }
            }
          }

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

      &.annotation {
        padding-left: 0;

        .attribute-col-title {
          padding-left: 0;
        }
      }

      &.scan {
        padding-left: 15px;

        .attribute-col-title {
          padding-left: 15px;
        }

        .attribute-col-body {
          flex-direction: row;
        }
      }

    }
  }
  .tree-row {
    margin-bottom: 60px;

    .cases-list-col {
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
          text-align: right;
        }

      }

      .pagination-row {
        border-top: solid #e4dfcb 1px;
        border-bottom: solid #e4dfcb 1px;
      }

      .cases-list-row {
        margin-bottom: 30px;
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
