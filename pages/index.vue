<template>
<b-row class="main-row">
  <b-container>
  <b-row class="search-row">
    <SearchTabs/>
  </b-row>
  <b-row class="service-section">
    <b-row class="home-section-title">услуги</b-row>
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


</b-container>
</b-row>
</template>

<script>
import SearchTabs from "~/components/SearchTabs";

export default {
  components: {SearchTabs}
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
        background: url("~assets/svg/decor 1.svg") left no-repeat;
        background-size: 86px;
        padding-top: 20px;
        padding-bottom: 15px;
        padding-left: 20px;

    }
    .service-section {
      flex-direction: column;
      margin-top: 40px;

      .service-section-row {
        justify-content: space-between;
        margin-top: 40px;
        .section-card {
          width: 100%;
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


}
</style>
