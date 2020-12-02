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



  </b-container>

</div>
</template>

<script>
import PageTitleInner from "@/components/PageTitleInner";
import BreadCrumbs from "@/components/BreadCrumbs";
export default {
  name: "fundsType",
  components: {BreadCrumbs, PageTitleInner},
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
      }
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


    }
  }
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
}

/* ПК версия -  от 1024 px*/
@media (min-width: 1024px) {

}
</style>
