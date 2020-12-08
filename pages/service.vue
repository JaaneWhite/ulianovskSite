<template>
<div>
<page-title :page-title-text="pageTitleText" />
  <b-container>
    <b-row class="breadcrumb-row">
      <bread-crumbs :bread-crumb-items="breadCrumbItems"></bread-crumbs>
    </b-row>
  <b-row class="main-content-row">
    <b-col cols="12" xl="10" class="service-desc-col">
      <section-title :section-title-text="descTitle" class="bg-1"></section-title>
      <b-row class="service-text">
        <p>Услуга «Просмотр цифровых копий архивных документов» позволяет зарегистрированным пользователям просматривать оцифрованные документы ГАТО и тематические базы данных после внесения оплаты.</p>
        <p>В описании каждого отсканированного дела в электронном каталоге есть атрибут "Дело отсканировано полностью?"</p>
        <p>Есть не полностью отсканированные дела. В их описаниях написано "Дело отсканировано полностью? = НЕТ"</p>
      </b-row>
      <b-row class="service-attn">
        <b-col cols="2" md="1" class="attn-img-col"><b-img src="~/assets/svg/alert.svg" class="attn-icon"></b-img></b-col>
        <b-col cols="10" md="11" class="attn-text-col">
          <p>Внимание!</p>
          <p>Отсканировано примерно 10% дел ГУ ГАТО!  Если дело не отсканировано, кнопки "Читать документ" нет.</p>
        </b-col>
      </b-row>
      <section-title :section-title-text="howToTitle" class="bg-2"></section-title>
      <b-row class="how-to-text">
        <p>1. Зарегистрироваться и авторизоваться на нашем сайте;</p>
        <p>2. Оплатить абонемент онлайн банковской картой или на р/с архива;</p>
      </b-row>
      <b-row class="how-to-note">
        Перед оплатой можно редактировать количество часов в абонементах с помощью  "+" и "-".
      </b-row>
      <b-row class="how-to-text">
        <p>3. Активировать купленный абонемент.</p>
      </b-row>
      <b-row class="how-to-note">
        Для активации абонемента необходимо оплатить услугу банковской картой или выслать квитанциию об оплате
        (копию в формате jpg  или pdf) на электронный адрес &nbsp; <b-link to=""> statearchiv.iat@tularegion.org.</b-link>
        После проверки квитанции на Ваш электронный адрес придет уведомление "Абонемент активирован".
      </b-row>
      <b-row class="how-to-text">
        <p>После активации абонемента запускается таймер обратного отсчета времени, без возможности приостановки. Например, если  активированы 2 часа, они будут полностью израсходованы. Если Вы планируете работать на сайте продолжительный промежуток времени целесообразно набирать абонемент с разбивкой на интервалы, кратные 1 часу, 2 часам (например, пять часов можно активировать разными способами: 1+1+1+1+1; 2+1+1+1; 2+1+2 …). </p>
      </b-row>
    </b-col>
    <b-col cols="12" xl="2" class="subscription-col">
      <b-row class="subscription-title">абонементы</b-row>
      <b-row>
      <b-row class="subscription-row">
        <b-col cols="6" md="12" class="subscription-time">
          <b-img src="~/assets/svg/clock 1.svg" class="subs-icon"></b-img>
          <div class="subs-time-text"><div class="subs-time-num"> 1 </div>ч.&nbsp;=&nbsp;<b>24 ₽</b></div>

        </b-col>
        <b-col cols="6" md="12" class="subscription-btn">
          <b-button class="subs-button" to="">Купить</b-button>
        </b-col>
      </b-row>
      <b-row class="subscription-row">
        <b-col cols="6" md="12" class="subscription-time">
          <b-img src="~/assets/svg/clock 2.svg" class="subs-icon"></b-img>
          <div class="subs-time-text"><div class="subs-time-num"> 2 </div>ч.&nbsp;=&nbsp;<b>48 ₽</b></div>

        </b-col>
        <b-col cols="6" md="12" class="subscription-btn">
          <b-button class="subs-button" to="">Купить</b-button>
        </b-col>
      </b-row>
      <b-row class="subscription-row">
        <b-col cols="6" md="12" class="subscription-time">
          <b-img src="~/assets/svg/clock 5.svg" class="subs-icon"></b-img>
          <div class="subs-time-text"><div class="subs-time-num"> 5 </div>ч.&nbsp;=&nbsp;<b>120 ₽</b></div>

        </b-col>
        <b-col cols="6" md="12" class="subscription-btn">
          <b-button class="subs-button" to="">Купить</b-button>
        </b-col>
      </b-row>
      <b-row class="subscription-row">
        <b-col cols="6" md="12" class="subscription-time">
          <b-img src="~/assets/svg/clock 10.svg" class="subs-icon"></b-img>
          <div class="subs-time-text"><div class="subs-time-num"> 10 </div>ч.&nbsp;=&nbsp;<b>240 ₽</b></div>

        </b-col>
        <b-col cols="6" md="12" class="subscription-btn">
          <b-button class="subs-button" to="">Купить</b-button>
        </b-col>
      </b-row>
      </b-row>

    </b-col>
    <b-col cols="12" class="service-conditions-col">
      <section-title :section-title-text="condTitle" class="bg-3"></section-title>
      <b-row class="service-cond-row">
        <b-col cols="2" md="1" class="cond-icon-col">
          <b-img src="~/assets/svg/doc.svg" class="cond-icon"></b-img>
        </b-col>
        <b-col cols="10" md="11" class="cond-text-col">
          <p>Прейскурант услуг ГУ ГАТО, </p>
          <b-link>Скачать (18Кб)</b-link>
        </b-col>
      </b-row>
      <b-row class="service-cond-row">
        <b-col cols="2" md="1" class="cond-icon-col">
          <b-img src="~/assets/svg/doc.svg" class="cond-icon"></b-img>
        </b-col>
        <b-col cols="10" md="11" class="cond-text-col">
          <p>Публичная оферта на заключение договора возмездного оказания услуг государственного учреждения «Государственный архив Тульской области», </p>
          <b-link>Скачать (34Кб)</b-link>
        </b-col>
      </b-row>
      <b-row class="service-cond-row">
        <b-col cols="2" md="1" class="cond-icon-col">
          <b-img src="~/assets/svg/doc.svg" class="cond-icon"></b-img>
        </b-col>
        <b-col cols="10" md="11" class="cond-text-col">
          <p>Условия передачи и обработки персональных данных, </p>
          <b-link>Скачать (18Кб)</b-link>
        </b-col>
      </b-row>

    </b-col>
    <b-col cols="12" class="other-service-col">
      <section-title :section-title-text="otherTitle" class="bg-4" />
      <b-row class="other-links">
        <b-link to="" class="other-link">Подать запрос</b-link>
        <b-link to="" class="other-link">Направить заказ</b-link>
        <b-link to="" class="other-link">Требования на выдачу дел в читальном зале</b-link>

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
import SectionTitle from "@/components/SectionTitle";
import JoinUs from "@/components/JoinUs";
export default {
  name: "service",
  components: {JoinUs, SectionTitle, BreadCrumbs, PageTitle},
  data() {
    return {
      pageTitleText: 'заказ цифровых копий архивных документов',
      descTitle: 'описание',
      howToTitle: 'КАК ПОЛУЧИТЬ УСЛУГУ',
      condTitle: 'УСЛОВИЯ ПРЕДОСТАВЛЕНИЯ УСЛУГ',
      otherTitle: 'ДРУГИЕ УСЛУГИ АРХИВА',
      breadCrumbItems: [
        {
          text: 'Главная',
          to: '/'
        },
        {
          text: 'Услуги – Просмотр цифровых копий архивных документов',
          active: true
        }
      ],
    }
  }
}
</script>

<style lang="scss">
/* по умолчанию -  мобильная версия - 0 - 767 px*/
@media (min-width: 0) {
  .main-content-row {
    margin-bottom: 30px;
    .service-desc-col {
      padding-right: 15px;
      padding-left: 0;
      .service-text {
        padding-left: 15px;
        padding-right: 15px;
        font-size: 15px;
        color: #474435;
      }
      .service-attn {
          .attn-img-col {
            .attn-icon {
              width: 35px;
            }
          }
          .attn-text-col {
            font-weight: bold;
            font-size: 15px;
            p {
              margin-bottom: 0;
            }
          }
        }
      .how-to-text {
        font-size: 16px;
        color: #949182;
        padding: 15px;
        padding-bottom: 0;
      }
      .how-to-note {
        background-color: #edeadb;
        font-size: 16px;
        color: #949182;
        font-style: italic;
        margin-right: -15px;
        padding: 15px;
        a {
          width: fit-content;
          border-bottom: dashed #474334 1px;
          text-decoration: none;
          &:hover {
            border-bottom: dashed #9e0000 1px;
          }

        }

      }
      }
    .subscription-col {
      background-color: #ebe8da;
      padding-top: 30px;
      padding-bottom: 30px;
      .subscription-title {
        text-align: center;
        margin: auto;
        width: fit-content;
        font-size: 30px;
        font-family: 'Oswald', sans-serif;
        color: #9e0000;
        font-weight: bold;
        text-transform: uppercase;
      }
      .subscription-row {
        margin-top: 15px;
        margin-bottom: 15px;
        width: 100%;
        .subscription-time {
          flex-direction: row;
          display: flex;
          padding: 0;
          font-size: 15px;
          .subs-icon {
            width: 27px;
          }
          .subs-time-text {
            display: flex;
            align-items: center;
            margin-left: 15px;
            .subs-time-num {
              font-size: 22px;
              font-weight: bold;
            }
          }

        }
        .subscription-btn {
          padding: 0;
          text-align: right;
          display: flex;
          .subs-button {
            height: 45px;
            width: 105px;
            background-color: black;
            color: white;
            font-weight: bold;
            border-radius: 0;
            border: none;
            margin-left: auto;
            margin-right: 0;
            box-shadow: none;
            &:hover, &:active, &:focus {
              background-color: white;
              color: black;
            }
          }

        }
      }
    }
    .service-conditions-col {
      padding-right: 15px;
      padding-left: 0;
      .service-cond-row {
        margin-top: 20px;
        .cond-icon-col {
          .cond-icon {
            width: 25px;
          }
        }
        .cond-text-col {
          padding: 0;
          font-size: 16px;
          p {
            margin-bottom: 0;
          }
          a {
            font-weight: bold;
            text-decoration: none;
            border-bottom: dashed #474334 1px;
            &:hover {
              border-bottom: dashed #9e0000 1px;
            }
          }

        }
      }
    }
    .other-service-col {
      padding-right: 15px;
      padding-left: 0;
      .other-links {
        flex-direction: column;
        padding-left: 15px;
        .other-link {
          font-size: 15px;
          color: #202020;
          text-decoration: underline;
          margin-bottom: 15px;
        }
      }
    }
    }
  }
/* планшетная версия - 768 - 1023 px*/
@media (min-width: 768px) {
  .service-attn {
    margin-bottom: 30px;
  }
  .main-content-row {
    .subscription-col {
      flex-direction: column;
      display: flex;
      margin-bottom: 30px;

      .subscription-title {
        width: 100%;
      }

      .subscription-row {
        width: 25%;

        .subscription-time {
          display: flex;
          flex-direction: column;
          text-align: center;
          .subs-icon {
            margin-right: auto;
            margin-left: auto;
            width: 50px;
          }
          .subs-time-text {
            margin-right: auto;
            margin-left: auto;
          }
        }
        .subscription-btn {
          text-align: center;
          .subs-button {
            width: 150px;
            margin-right: auto;
            margin-left: auto;
          }

        }
      }
    }
    .service-conditions-col {
      margin-bottom: 30px;
    }
  }

}
/* ПК версия -  от 1024 px*/
@media (min-width: 1024px) {
  .main-content-row {
    .subscription-col {
      flex-direction: column;
      display: flex;
      margin-bottom: 0;
      background-color: transparent;
      padding: 0;

      .subscription-title {
        width: 100%;
        margin-top: 0;
        padding-top: 15px;
        margin-bottom: 0;
        margin-left: auto;
        margin-right: auto;
        text-align: center;
        background-color: #ebe8da;
        padding-left: 15px;
      }

      .subscription-row {
        width: 50%;
        background-color: #ebe8da;
        margin-top: 0;
        margin-bottom: 0;
        padding-top: 15px;
        padding-bottom: 15px;

        .subscription-time {
          display: flex;
          flex-direction: column;
          text-align: center;
          .subs-icon {
            margin-right: auto;
            margin-left: auto;
            width: 50px;
          }
          .subs-time-text {
            margin-right: auto;
            margin-left: auto;
          }
        }
        .subscription-btn {
          text-align: center;
          .subs-button {
            width: 105px;
            margin-right: auto;
            margin-left: auto;
          }

        }
      }
    }
    .service-conditions-col {
      margin-bottom: 30px;
    }
  }

}

</style>
