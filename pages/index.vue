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
    <b-row class="news-section">
      <b-col cols="8" class="news-title-col">
      <b-row class="home-section-title news-title">Новости</b-row>
      </b-col>
      <b-col cols="4" class="news-title-col-all">
        <b-link to="" class="all-news-link">Все новости</b-link>
      </b-col>
      <b-row class="news-block">
        <b-col cols="12" xl="5" class="main-news">
          <b-row>
            <b-col cols="2" class="news-date-col">
              <b-row class="news-date-date">05</b-row>
              <b-row class="news-date-month">ноя</b-row>
              <b-row class="news-date-month">2020</b-row>
            </b-col>
            <b-col cols="10" class="news-body-col">
              <b-img src="~assets/img/home/news main.png"></b-img>
              <b-link class="main-news-title" to="">В архиве продолжаются занятия по внедрению новых Правил</b-link>
              <b-row class="main-news-text">14 октября 2020 года состоялось очередное плановое занятие по изучению «Правил организации хранения, комплектования, учета и использования документов АФ РФ и других архивных документов, 2020 г.» для сотрудников госархива и видео занятие для коллег из муниципальных архивов Ульяновской области на тему «Система справочно-поисковых средств». Занятие провела главный архивист отдела...</b-row>

            </b-col>
          </b-row>
        </b-col>
        <b-col cols="12" xl="7" class="other-news">
          <b-row class="other-news-row">
            <b-col cols="2" xl="1" class="news-date-col">
              <b-row class="news-date-date">02</b-row>
              <b-row class="news-date-month">сен</b-row>
              <b-row class="news-date-month">2020</b-row>
            </b-col>
            <b-col cols="10" xl="11" class="news-body-col">
              <b-row style="margin-bottom: 40px">
                <b-col cols="12" xl="5" style="padding: 0">
                  <b-img src="~assets/img/home/news-1.png"></b-img>
                </b-col>
                <b-col cols="12" xl="7" style="padding: 0">
                  <b-link class="main-news-title" to=""><div>Государственный архив Ульяновской области  принимает участие в реализации проекта по историческому ... </div></b-link>
                  <b-row class="main-news-text">1 сентября 2020 года в Ульяновской области стартовал проект «Уроки исторической памяти», направленный на повышение уровня знаний.</b-row>
                </b-col>
              </b-row>
            </b-col>
          </b-row>
          <b-row class="other-news-row">
            <b-col cols="2" xl="1" class="news-date-col">
              <b-row class="news-date-date">02</b-row>
              <b-row class="news-date-month">сен</b-row>
              <b-row class="news-date-month">2020</b-row>
            </b-col>
            <b-col cols="10" xl="11" class="news-body-col">
              <b-row style="margin-bottom: 40px">
                <b-col cols="12" xl="5" style="padding: 0">
                  <b-img src="~assets/img/home/news-1.png"></b-img>
                </b-col>
                <b-col cols="12" xl="7" style="padding: 0">
                  <b-link class="main-news-title" to=""><div>Государственный архив Ульяновской области  принимает участие в реализации проекта по историческому ... </div></b-link>
                  <b-row class="main-news-text">1 сентября 2020 года в Ульяновской области стартовал проект «Уроки исторической памяти», направленный на повышение уровня знаний.</b-row>
                </b-col>
              </b-row>
            </b-col>
          </b-row>
          <b-row class="other-news-row">
            <b-col cols="2" xl="1" class="news-date-col">
              <b-row class="news-date-date">02</b-row>
              <b-row class="news-date-month">сен</b-row>
              <b-row class="news-date-month">2020</b-row>
            </b-col>
            <b-col cols="10" xl="11" class="news-body-col">
              <b-row style="margin-bottom: 40px">
                <b-col cols="12" xl="5" style="padding: 0">
                  <b-img src="~assets/img/home/news-1.png"></b-img>
                </b-col>
                <b-col cols="12" xl="7" style="padding: 0">
                  <b-link class="main-news-title" to=""><div>Государственный архив Ульяновской области  принимает участие в реализации проекта по историческому ... </div></b-link>
                  <b-row class="main-news-text">1 сентября 2020 года в Ульяновской области стартовал проект «Уроки исторической памяти», направленный на повышение уровня знаний.</b-row>
                </b-col>
              </b-row>
            </b-col>
          </b-row>

        </b-col>


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
    .news-section {
      margin-top: 40px;
      .news-title-col {
        padding: 0;
      }
      .news-title-col-all {
        padding: 0;
        display: flex;
      }

      .news-title {
        background: url("~assets/svg/decor 3.svg") left no-repeat;
        background-size: 82px;
        padding-top: 20px;
        padding-bottom: 15px;
        padding-left: 20px;
      }
      .all-news-link {
        margin: auto 0 auto auto;
        padding-right: 15px;
        background-image: url("~assets/img/arrow right.png");
        background-position: right;
        background-repeat: no-repeat;
        font-size: 16px;
        font-weight: bold;
        text-decoration: underline;
        color: #949081;
        &:hover {
          color: #9e0000;
        }


      }
      .news-block {
        width: 100%;
        .main-news {
          padding: 0;
          .news-date-col {
            padding: 0;
            display: flex;
            flex-direction: column;
            .news-date-date {
              font-size: 40px;
              font-family: Oswald, sans-serif;
              color: #474334;
              font-weight: bold;
              text-transform: uppercase;
              line-height: 0.9;
              margin-left: auto;
              margin-right: auto;
              margin-top: 25px;
              border-top: solid #474334 2px;
              padding-top: 10px;

            }
            .news-date-month {
              font-size: 18px;
              font-family: Oswald, sans-serif;
              color: #474334;
              text-transform: uppercase;
              line-height: 1.556;
              margin-left: auto;
              margin-right: auto;


            }
          }
          .news-body-col {
            padding: 0 15px 0 0;

            img {
              width: 100%;
              margin-bottom: 15px;
            }
            .main-news-title {

              font-size: 20px;
              font-family: Roboto, sans-serif;
              color: #474334;
              font-weight: bold;
              line-height: 1.417;
              &:hover {
                color: #9e0000;
                text-decoration: none;
              }

            }
            .main-news-text {
              margin-top: 15px;
              font-size: 12px;
              font-family: Roboto, sans-serif;
              color: #474334;
              line-height: 1.625;
            }
          }
        }
        .other-news {
          padding: 0;
          margin-top: 30px;
          .news-date-col {
            padding: 0;
            display: flex;
            flex-direction: column;
            .news-date-date {
              font-size: 40px;
              font-family: Oswald, sans-serif;
              color: #474334;
              font-weight: bold;
              text-transform: uppercase;
              line-height: 0.9;
              margin-left: auto;
              margin-right: auto;
              margin-top: 35px;

            }
            .news-date-month {
              font-size: 18px;
              font-family: Oswald, sans-serif;
              color: #474334;
              text-transform: uppercase;
              line-height: 1.556;
              margin-left: auto;
              margin-right: auto;


            }
          }
          .news-body-col {
            padding: 0;
            padding-right: 15px;
            img {
              width: 100%;
            }
            .main-news-title {

              font-size: 16px;
              font-family: Roboto, sans-serif;
              color: #474334;
              font-weight: bold;
              line-height: 1.417;
              &:hover {
                color: #9e0000;
                text-decoration: none;
              }
              div {
                max-height: 65px;
                overflow: hidden;
                text-overflow: ellipsis;
                margin-top: 30px;
              }
            }
            .main-news-text {
              margin-top: 20px;
              font-size: 12px;
              font-family: Roboto, sans-serif;
              color: #474334;
              line-height: 1.625;
              max-height: 75px;
              overflow: hidden;
              text-overflow: ellipsis;
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
  .news-section {
    margin-top: 40px;

    .news-title {
      background: url("~assets/svg/decor 3.svg") left no-repeat;
      background-size: 82px;
      padding-top: 20px;
      padding-bottom: 15px;
      padding-left: 20px;
    }
  }


}
@media (min-width: 1024px) {
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
  .news-section {
    .news-block {
      .main-news {
        .news-body-col {
          padding-right: 40px;

          img {
            margin-bottom: 30px;
          }

          .main-news-title {
            font-size: 24px;
          }

          .main-news-text {
            margin-top: 30px;
            font-size: 16px;
          }
        }
      }

      .other-news {
        margin-top: 0;
        .other-news-row {
          &:hover {
            .news-body-col {
              img {
                opacity: 50%;
              }

              .main-news-title {
                color: #9e0000;
              }
            }
          }
        }


        .news-body-col {
          padding-right: 40px;
          flex-direction: column;
          img {
            width: 100%;
          }
          .main-news-title {
            font-size: 20px;
            div {
              max-height: 85px;
              margin-top: 0;
              padding-left: 30px;
            }
          }
          .main-news-text {
            margin-top: 20px;
            font-size: 16px;
            max-height: 80px;
            padding-left: 30px;
          }
        }
      }
    }


  }
}
</style>
