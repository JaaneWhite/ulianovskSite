<template>
<div>
  <join-us />
<b-container>

  <b-row class="main-content-row">
    <section-title :section-title-text="pageTitleText" class="bg-1 fs-sm" />
    <b-col cols="12" xl="6" class="img-col-404">
      <b-img src="~/assets/svg/noy found.svg" class="404-img"></b-img>
    </b-col>
    <b-col cols="12" xl="6" class="text-col-404">
      <p><b>Документ по данному адресу не найден.</b></p>
      <p>Возможно, он был перемещен, удален или же адрес был введен не верно.</p>
      <p>Для поиска необходимой информации вы можете:</p>
      <p class="list-item-404">вернуться <b-link to=""> назад </b-link>,</p>
      <p class="list-item-404">перейти <b-link to="/"> на главную страницу</b-link>,</p>
      <p class="list-item-404">воспользоваться меню в верхней части сайта,</p>
      <p class="list-item-404">воспользоваться формой поиска ниже.</p>
    </b-col>
    <search-tile :search-tile-title="searchTileTitle" class="lg"/>
  </b-row>

</b-container>
  <search-tile :search-tile-title="searchTileTitle" class="sm-md"/>
</div>
</template>

<script>
import SectionTitle from "@/components/SectionTitle";
import SearchTile from "@/components/SearchTile";
import JoinUs from "@/components/JoinUs";
export default {
  name: "404",
  components: {JoinUs, SearchTile, SectionTitle},
  data() {
    return {
      pageTitleText: 'ошибка 404: страница не найдена',
      searchTileTitle: 'Поиск документов',
    }
  }
}
</script>

<style lang="scss">
/* по умолчанию -  мобильная версия - 0 - 767 px*/
@media (min-width: 0) {
  .lg {
    display: none;
  }
  .main-content-row {
    margin-top: 30px;
    .img-col-404 {

  }
    .text-col-404 {
      font-size: 16px;
      p {
        &.list-item-404 {
          background-image: url("~assets/img/Ellipse 1.png");
          background-repeat: no-repeat;
          background-position-y: 8px;
          padding-left: 30px;
        }
        a {
          text-decoration: underline;
          font-weight: bold;
        }
      }

    }
  }
}
/* планшетная версия - 768 - 1023 px*/
@media (min-width: 768px) {
  .main-content-row {
    margin-top: 30px;

    .img-col-404 {

    }

    .text-col-404 {
      font-size: 20px;

      p {
        &.list-item-404 {
          background-position-y: 8px;
        }

      }
    }
  }
}

/* ПК версия -  от 1024 px*/
@media (min-width: 1024px) {
  .sm-md {
    display: none;
  }
  .lg {
    display: flex;
    width: 100%;
    margin-top: 30px;
  }
  .main-content-row {
    margin-bottom: 60px;
  }
}
</style>
