<template>
<div>
  <page-title :page-title-text="pageTitleText"></page-title>
  <b-container>
    <b-row class="breadcrumb-row">
      <bread-crumbs :bread-crumb-items="breadCrumbItems" />
    </b-row>
    <b-row class="main-content-row">
      <b-col cols="12" md="12" class="contacts-col">
      <b-row class="home-section-title bg-1">{{pageTitleText}}</b-row>
      <b-row>
        <b-col cols="12" md="6" xl="3">
          <b-img class="contact-image" src="~assets/img/contacts/img-1.png"></b-img>
        </b-col>
        <b-col cols="12" md="6" class="contact-block">
        <b-row class="contact-info">
          <b-col cols="2" md="1" class="contact-image-col">
            <b-img src="~/assets/svg/tel b.svg" class="contact-icon"></b-img>
          </b-col>
          <b-col cols="10" md="11" class="contact-text-col">
            <b-row class="contact-text">Приемная (тел./факс): +7(8422)&nbsp73-56-03</b-row>
            <b-row class="contact-text">Прием граждан (тел): +7(8422)&nbsp73-56-03</b-row>
            <b-row class="contact-text">Читальный зал (тел.): +7(8422)&nbsp73-57-88</b-row>
          </b-col>
        </b-row>
        <b-row class="contact-info">
          <b-col cols="2" md="1" class="contact-image-col">
            <b-img src="~/assets/svg/email b.svg" class="contact-icon"></b-img>
          </b-col>
          <b-col cols="10" md="11" class="contact-text-col">
            <b-row class="contact-text">
              <b-link to="">ogugauo@mail.ru</b-link>
            </b-row>
          </b-col>
        </b-row>
        <b-row class="contact-info">
          <b-col cols="2" md="1" class="contact-image-col">
            <b-img src="~/assets/svg/adress b.svg" class="contact-icon"></b-img>
          </b-col>
          <b-col cols="10" md="11" class="contact-text-col">
            <b-row class="contact-text">432017, г. Ульяновск, ул. 12 Сентября, д. 7а</b-row>
          </b-col>
        </b-row>
      </b-col>
      </b-row>

      </b-col>
      <b-col cols="12" md="6" xl="4" class="contacts-col">

        <b-row>
          <b-col cols="12" class="home-section-title bg-2">режим работы архива</b-col>
          <b-col cols="12" md="12">
            <b-img class="contact-image" src="~assets/img/contacts/img-2.png"></b-img>
          </b-col>

          <b-col cols="12" md="12" class="contact-block">
          <b-row class="contact-info">
            <b-col cols="2" md="1" class="contact-image-col">
              <b-img src="~/assets/svg/clock b.svg" class="contact-icon"></b-img>
            </b-col>
            <b-col cols="10" md="11" class="contact-text-col">
              <b-row class="contact-text">ПН - ЧТ: 8<sup>00</sup> - 17<sup>00</sup></b-row>
              <b-row class="contact-text">ПТ: 08<sup>00</sup> - 16<sup>00</sup></b-row>
              <b-row class="contact-text">Перерыв на обед: 12<sup>00</sup> – 13<sup>00</sup></b-row>
              <b-row class="contact-text">Выходные – СБ, ВС</b-row>
            </b-col>
          </b-row>
        </b-col>
        </b-row>

      </b-col>
      <b-col cols="12" md="6" xl="4" class="contacts-col">


        <b-row>
          <b-col cols="12" class="home-section-title bg-3">читальный зал</b-col>
          <b-col cols="12" md="12">
        <b-img class="contact-image" src="~assets/img/contacts/img-3.png"></b-img>
          </b-col>
        <b-col cols="12" md="12" class="contact-block">
          <b-row class="contact-info">
            <b-col cols="2" md="1" class="contact-image-col">
              <b-img src="~/assets/svg/clock b.svg" class="contact-icon"></b-img>
            </b-col>
            <b-col cols="10" md="11" class="contact-text-col">
              <b-row class="contact-text">ПН - СР: 9<sup>00</sup> - 16<sup>00</sup></b-row>
              <b-row class="contact-text">ЧТ: 12<sup>00</sup> - 19<sup>00</sup></b-row>
              <b-row class="contact-text">ПТ: 09<sup>00</sup> - 15<sup>00</sup></b-row>
              <b-row class="contact-text note">Санитарный день: 4-ая  ПТ каждого месяца</b-row>
            </b-col>
          </b-row>
        </b-col>
        </b-row>
      </b-col>
      <b-col cols="12" md="6" xl="4" class="contacts-col">
        <b-row class="home-section-title bg-4">приём граждан</b-row>
        <b-row>
          <b-col cols="12" md="12">
            <b-img class="contact-image" src="~assets/img/contacts/img-4.png"></b-img>
          </b-col>
          <b-col cols="12" md="12" class="contact-block">
          <b-row class="contact-info">
            <b-col cols="2" md="1" class="contact-image-col">
              <b-img src="~/assets/svg/clock b.svg" class="contact-icon"></b-img>
            </b-col>
            <b-col cols="10" md="11" class="contact-text-col">
              <b-row class="contact-text">ПН - ЧТ: 9<sup>00</sup> - 16<sup>00</sup></b-row>
              <b-row class="contact-text">ПТ: 09<sup>00</sup> - 15<sup>00</sup></b-row>
              <b-row class="contact-text">Личный приём руководителя:</b-row>
              <b-row class="contact-text"><b>Денисова Ольга Ивановна</b>(директор)</b-row>
              <b-row class="contact-text">ВТ: 09<sup>00</sup> - 16<sup>00</sup></b-row>
            </b-col>
          </b-row>
        </b-col>
        </b-row>
      </b-col>

    </b-row>

  </b-container>
  <join-us />
</div>
</template>

<script>
import PageTitle from "@/components/PageTitle";
import BreadCrumbs from "@/components/BreadCrumbs";
import JoinUs from "@/components/JoinUs";
export default {
  name: "contacts",
  components: {JoinUs, BreadCrumbs, PageTitle},
  data() {
    return {
      pageTitleText: 'Контакты',
      breadCrumbItems: [
        {
          text: 'Главная',
          to: '/'
        },
        {
          text: 'Об архиве – Контакты',
          active: true
        }
      ],
    }
  }
}
</script>

<style lang="scss" scoped>
/* по умолчанию -  мобильная версия - 0 - 767 px*/
@media (min-width: 0) {
  .main-content-row {
    .contacts-col {
      padding: 0;
      .home-section-title {
        font-size: 30px;
        font-family: 'Oswald', sans-serif;
        color: #474335;
        padding-left: 15px;
        margin-left: 0px;
        padding-top: 15px;
        padding-bottom: 15px;
        line-height: 1.2;
        &.bg-1 {
          background: url("~assets/svg/decor 1.svg") left no-repeat;
          background-size: 70px;
        }
        &.bg-2 {
          background: url("~assets/svg/decor 2.svg") left no-repeat;
          background-size: 75px;
          background-position-y: top;
          padding-left: 30px;
          margin-left: -15px;
        }
        &.bg-3 {
          background: url("~assets/svg/decor 3.svg") left no-repeat;
          background-size: 70px;
        }
        &.bg-4 {
          background: url("~assets/svg/decor 4.svg") left no-repeat;
          background-size: 80px;
        }

      }
      .contact-image {
        width: 100%;
        margin-bottom: 30px;
      }
      .contact-info {
        width: 100%;
        .contact-image-col {
          padding-left: 0;
          padding-right: 0;
          .contact-icon {
            width: 20px;
            height: 20px;
            margin-bottom: auto;
          }
        }
        .contact-text-col {
          padding-left: 0;
          .contact-text {
            margin-bottom: 20px;
            font-size: 15px;
            a{
              font-weight: bold;
              text-decoration: none;
              border-bottom: dashed #474334 1px;
            }
            sup {
              top: 0.5em;
            }
            &.note {
              font-style: italic;
              color: #949182;
            }



          }
        }
      }
    }


  }

}
/* планшетная версия - 768 - 1023 px*/
@media (min-width: 768px) {
  .main-content-row {
    margin-left: 0;
    margin-right: 0;

    .contacts-col {
      padding: 0;
      flex-direction: row;

      .home-section-title {
        padding-left: 20px;
        margin-left: -20px;
        padding-top: 15px;
        padding-bottom: 15px;
        margin-bottom: 30px;
        width: 100%;
        padding-right: 0;

        &.bg-1 {
          background-size: 100px;
        }

        &.bg-2 {
          background: url("~assets/svg/decor 2.svg") left no-repeat;
          background-size: 100px;
          background-position-y: center;
          padding-left: 30px;
          margin-left: -30px;
        }

        &.bg-3 {
          background: url("~assets/svg/decor 3.svg") left no-repeat;
          background-size: 100px;
        }

        &.bg-4 {
          background: url("~assets/svg/decor 4.svg") left no-repeat;
          background-size: 100px;
        }

      }

      .contact-image {
        margin-bottom: 30px;
        height: auto;
        margin-left: -15px;

      }

      .contact-block {
        width: 50%;
        margin-bottom: 30px;
        padding-left: 0;
      }

      .contact-info {
        width: 100%;

      }
    }
  }
}

/* ПК версия -  от 1024 px*/
@media (min-width: 1024px) {
}

</style>
