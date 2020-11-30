<template>
<b-row class="main-row">
  <b-container>
  <b-row class="search-row">
    <SearchTabs/>
  </b-row>
  <b-row class="service-section">
    <b-row class="home-section-title service-title">услуги</b-row>
    <b-row class="service-section-row">
          <b-card class="section-card">
            <b-link to="" class="card-link">
              <b-card-img src="~assets/img/home/service1.png" class="card-img"></b-card-img>
              <b-card-text class="card-title">Социально-правовые и тематические запросы</b-card-text>
            </b-link>
          </b-card>
          <b-card class="section-card">
            <b-link to="" class="card-link">
              <b-card-img src="~assets/img/home/service2.png" class="card-img"></b-card-img>
              <b-card-text class="card-title">Заказ цифровых копий архивных документов</b-card-text>
            </b-link>
          </b-card>
          <b-card class="section-card">
            <b-link to="" class="card-link">
              <b-card-img src="~assets/img/home/service3.png" class="card-img"></b-card-img>
              <b-card-text class="card-title">Требования на выдачу дел в читальном зале</b-card-text>
            </b-link>
          </b-card>
    </b-row>

  </b-row>
    <b-row class="pop-section">
      <b-row class="home-section-title pop-title">Популярные разделы</b-row>
      <b-row class="pop-section-row">
        <b-card class="pop-tile">
          <b-link class="pop-tile-link" v-for="item in popItems.slice(0,1)" :to="item.link">{{item.text}}</b-link>
        </b-card>
        <b-card class="pop-tile">
          <b-link class="pop-tile-link" v-for="item in popItems.slice(1,2)" :to="item.link">{{item.text}}</b-link>
        </b-card>
        <b-card class="pop-list">
          <b-nav class="pop-list-group">
            <b-nav-item
              class="pop-list-item"
              v-for="item in popItems.slice(2,6)"
              :to="item.link"
            >{{item.text}}</b-nav-item>
          </b-nav>
        </b-card>
        <b-card cols="6" md="6" xl="3" class="pop-list">
          <b-nav class="pop-list-group">
            <b-nav-item
              class="pop-list-item"
              v-for="item in popItems.slice(6,10)"
              :to="item.link"
            >{{item.text}}</b-nav-item>
          </b-nav>
        </b-card>
      </b-row>
    </b-row>


</b-container>
</b-row>
</template>

<script>
import SearchTabs from "~/components/SearchTabs";

export default {
  components: {SearchTabs},
  data() {
    return {
      popItems: [
        {id:"0", text:"1870 - 1918 гг. Симбирский окружной суд г.Симбирск Симбирской губернии", link:""},
        {id:"1", text:"1906 - 1917 гг. Симбирская губернская землеустроительная комиссия Главного Управления землеустройства и земледелия г.Симбирск. 1918 г - ликвидирована", link:""},
        {id:"2", text:"Дореволюционные планы, карты и схемы", link:""},
        {id:"3", text:"Коломенская духовная консистория", link:""},
        {id:"4", text:"Перепись Евремова и Евремовского уезда", link:""},
        {id:"5", text:"Фонды новейшей истории Тульской", link:""},
        {id:"6", text:"Тульская духовная консистория", link:""},
        {id:"7", text:"Фонды церквей дореволюционного периода", link:""},
        {id:"8", text:"Скуратово", link:""},
        {id:"9", text:"Перепись Евремова и Евремовского уезда", link:""},
      ]
    }
  }
}
</script>

<style lang="scss">
/* по умолчанию -  мобильная версия - 0 - 767 px*/
@media (min-width: 0) {
    .home-section-title {
        font-size: 40px;
        font-family: "Oswald", sans-serif;
        color: rgb(71, 67, 52);
        font-weight: bold;
        text-transform: uppercase;
        line-height: 0.9;
        text-align: left;
    }
    .service-section {
      flex-direction: column;
      margin-top: 40px;
      .service-title {
        background: url("~assets/svg/decor 1.svg") left no-repeat;
        background-size: 86px;
        padding-top: 20px;
        padding-bottom: 15px;
        padding-left: 20px;
      }

      .service-section-row {
        justify-content: space-between;
        margin-top: 40px;
        .section-card {
          width: 100%;
          border-radius: 0;
          border: none;
          margin-bottom: 15px;
          .card-body {
            padding: 0 0 10%;
          }
          .card-link {
            .card-img {
              border-radius: 0;
            }
            .card-title {
              margin-left: 20px;
              position: absolute;
              bottom: 0;
              padding: 20px 30px;
              width: 75%;
              background-color: #2b2a25;
              color: white;
              font-size: 12px;
              text-transform: uppercase;
              font-family: 'Roboto', sans-serif;
              font-weight: bold;
            }
            &:hover {
              .card-title {
                background-color: #9e0000;
              }
              .card-img {
                opacity: 50%;
              }
            }


          }
        }

      }
    }
    .pop-section {
      margin-top: 40px;
      .pop-title {
        background: url("~assets/svg/decor 2.svg") left no-repeat;
        background-size: 120px;
        padding-top: 15px;
        padding-bottom: 20px;
        padding-left: 20px;
      }
      .pop-section-row {
        flex-direction: row;
        white-space: normal;
        .pop-tile {
          display: flex;
          border-radius: 0;
          border: none;
          .card-body {
            display: flex;
            background-color: #9e0000;
            margin: 15px;
            padding-left: 30px;
            padding-right: 30px;
            padding-top: 30px;
            padding-bottom: 30px;
            a {
              margin: auto;
              color: white;
              text-decoration: underline;
              font-size: 16px;
              font-family: 'Roboto', sans-serif;
            }
            &:hover {
              background-color: #c10000;
            }


          }



        }
        .pop-list {
          display: flex;
          border-radius: 0;
          border: none;
          .card-body {
            display: flex;
            margin: 15px;
            padding: 0;
            .pop-list-group {
              border-left: solid #474334 1px;
              padding-left: 40px;
              flex-direction: column;
              .pop-list-item {
                padding: 0;
                margin-bottom: 10px;
                .nav-link {
                  padding: 0;
                  font-size: 15px;
                  text-decoration: underline;
                  color: #474334;
                  &:hover {
                    color: #9e0000;
                  }


                }
              }
            }
          }
        }

      }
    }


  }


@media (min-width: 768px) {
  .main-row {
    background-image: url("~assets/img/bg.png");
    background-repeat: no-repeat;
    background-position: top;
    .search-row {
      height: 640px;
      padding-top: 60px;
    }
  }
  .home-section-title {
    padding-top: 20px;
    padding-bottom: 15px;
    padding-left: 20px;
    margin-left: -20px;

  }
  .service-section {
    margin-top: 40px;
    .service-title {

    }
    .service-section-row {
      .section-card {
        width: 33%;
        .card-body {
          padding: 0 0 10%;
        }
        .card-link {
          .card-img {
            border-radius: 0;
          }
          .card-title {
            padding: 10px 15px;
          }

        }
      }
    }
  }
  .pop-section {
    margin-top: 40px;
    .pop-title {
      background: url("~assets/svg/decor 2.svg") left no-repeat;
      background-size: 91px;
      padding-top: 15px;
      padding-bottom: 20px;
      padding-left: 40px;
      margin-left: -40px;
    }
    .pop-section-row {
      flex-direction: row;
      white-space: normal;

      .pop-tile {
        display: flex;
        max-width: 50%;

        a {
          margin: auto;
        }

      }
      .pop-list {
        display: flex;
        max-width: 50%;

        a {
          margin: auto;
        }

      }
    }
  }


}
@media (min-width: 1024px) {
  .search-row {

  }
  .service-section {
    margin-top: 60px;
    .service-section-row {
      margin-top: 40px;
      .section-card {
        width: auto;
        .card-body {
          padding: 0 0 10%;
        }
        .card-link {
          .card-img {
            border-radius: 0;
          }
          .card-title {
            padding: 20px 30px;
            width: 75%;
            font-size: 18px;
          }



        }
      }
    }
  }
  .pop-section {
    .pop-section-row {
      flex-direction: row;
      white-space: normal;

      .pop-tile {
        display: flex;
        max-width: 25%;

        a {
          margin: auto;
        }

      }
      .pop-list {
        max-width: 25%;

      }
    }
  }



}
</style>
