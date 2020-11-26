<template>
  <b-navbar toggleable="lg" class="top-menu-block">
    <b-navbar-toggle target="nav-collapse" class="burger-button"></b-navbar-toggle>
    <b-collapse id="nav-collapse" is-nav >
      <b-navbar-nav fill class="top-menu">
        <b-nav-item-dropdown href="#" class="top-menu-item" text="Путеводители">
          <b-container class="dropdown-menu-container">
            <b-dropdown-item href="#">Фонды досоветского периода</b-dropdown-item>
            <b-dropdown-item href="#">Фонды советского периода</b-dropdown-item>
          </b-container>
        </b-nav-item-dropdown>
        <b-nav-item-dropdown href="#" class="top-menu-item" text="Указатели">
          <b-container class="dropdown-menu-container">
            <b-dropdown-item href="#">Именной</b-dropdown-item>
            <b-dropdown-item href="#">Географический</b-dropdown-item>
          </b-container>
        </b-nav-item-dropdown>
        <b-nav-item href="#" class="top-menu-item">Муниципальные архивы <br> Ульяновской области</b-nav-item>
        <b-nav-item-dropdown href="#" class="top-menu-item" text="Тематические базы данных">
          <b-container class="dropdown-menu-container">
            <b-dropdown-item href="#">Дворяне Симбирской губернии</b-dropdown-item>
            <b-dropdown-item href="#">Ревизские сказки</b-dropdown-item>
            <b-dropdown-item href="#">Симбирское купечество</b-dropdown-item>
            <b-dropdown-item href="#">Клировые ведомости</b-dropdown-item>
            <b-dropdown-item href="#">Фотокаталог</b-dropdown-item>
            <b-dropdown-item href="#">Военнопленные</b-dropdown-item>
            <b-dropdown-item href="#">Захоронения</b-dropdown-item>
          </b-container>
        </b-nav-item-dropdown>
        <b-nav-item-dropdown href="#" class="top-menu-item" text="Услуги">
          <b-container class="dropdown-menu-container">
            <b-dropdown-item href="#">Социально-правовые и тематические запросы</b-dropdown-item>
            <b-dropdown-item href="#">Обслуживание пользователей в читальном зале</b-dropdown-item>
            <b-dropdown-item href="#">Приём документов от организаций, являющихся источниками комплектования архива</b-dropdown-item>
            <b-dropdown-item href="#">Составление информационных документов</b-dropdown-item>
            <b-dropdown-item href="#">Проведение информационных мероприятий</b-dropdown-item>
            <b-dropdown-item href="#">Предоставление документов организациям для экспонирования</b-dropdown-item>
            <b-dropdown-item href="#">Копирование документов и печатных изданий</b-dropdown-item>
            <b-dropdown-item href="#">Обеспечение сохранности и упорядочение документов организаций</b-dropdown-item>
          </b-container>
        </b-nav-item-dropdown>
        <b-nav-item-dropdown href="#" class="top-menu-item" text="Об архиве">
          <b-container class="dropdown-menu-container">
            <div class="dd-menu-item-title">Общие сведения</div>
            <b-dropdown-item href="#">История архива, Правовые документы</b-dropdown-item>
            <b-dropdown-item href="#">Список муниципальных архивов Ульяновской области, Вакансии</b-dropdown-item>

            <div class="dd-menu-item-title">Деятельность</div>
            <b-dropdown-item href="#">Рассекречивание</b-dropdown-item>
            <b-dropdown-item href="#">Планы развития архивного дела</b-dropdown-item>
            <b-dropdown-item href="#">Отчеты о выполнении плана развития архивного дела</b-dropdown-item>
            <b-dropdown-item href="#">Антикоррупционная деятельность</b-dropdown-item>
            <b-dropdown-item href="#">Источники комплектования</b-dropdown-item>
            <b-dropdown-item href="#">Отчёт о проведении специальной оценки условий труда</b-dropdown-item>
            <b-dropdown-item href="#">Планы мероприятий по охране труда</b-dropdown-item>

          </b-container>
        </b-nav-item-dropdown>
        <b-nav-item href="#" class="top-menu-item" text="">Контакты</b-nav-item>
      </b-navbar-nav>
    </b-collapse>

  </b-navbar>
</template>

<script>
export default {
  name: "TopMenu"
}
</script>

<style lang="scss">
/* по умолчанию -  мобильная версия - 0 - 767 px*/
@media (min-width: 0) {
  .top-menu-block {
    width: 100%;
    padding-right: 0;
    padding-left: 0;
    justify-content: flex-end;

    .burger-button {
      margin-right: 15px;
    }

    .top-menu {
      width: 100%;

      .top-menu-item {
        border: none;
        box-shadow: none;
        .nav-link {
          font-size: 15px;
          color: #474334;
          height: 100%;
          display: flex;
          align-items: center;
          text-align: left;
          border-bottom: solid 1px #949081;
          padding-right: 15px;
          padding-left: 15px;

        }
        &.show {
          .nav-link {
            color: white;
            background-color: #9e0000;
            border: none;
          }

        }
        .dropdown-toggle::after {
          display: none;
        }
        .dropdown-menu {
          border: none;
          border-radius: 0;
          margin: 0;
          padding: 0;
          left: 0;
          right: 0;
          top: auto;
          width: 100%;
          opacity: 100%;
          .dropdown-menu-container {
            background-color: #9e0000;
            padding: 0;
            flex-direction: column;
            text-align: right;
            align-items: flex-end;

            .dropdown-item {
              color: white;
              font-size: 15px;
              line-height: 1.733;
              white-space: normal;
              width: 100%;

              &:hover {
                color: #daa3a3;
                background-color: transparent;
              }

            }
            .dd-menu-item-title {
              color: #daa3a3;
              font-size: 15px;
              width: 100%;
              border-bottom: #daa3a3 solid 1px;
              text-align: left;
              padding-left: 30px;
              padding-top: 15px;

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
  .top-menu-block {
    width: 100%;
    padding-right: 0;
    padding-left: 0;
    justify-content: space-between;

    .top-menu {
      width: 100%;
      height: 50px;

      .top-menu-item {
        height: 100%;
        border: none;
        box-shadow: none;
        .nav-link {
          font-size: 15px;
          color: #474334;
          height: 100%;
          display: flex;
          align-items: center;
          text-align: center;

          &:hover {
            font-size: 15px;
            color: white;
            background-color: #9e0000;
          }
          &:focus {
            border: none;
            box-shadow: none;
            outline: none;
          }

        }
        &.show {
          .nav-link {
            color: white;
            background-color: #9e0000;
          }

        }
        .dropdown-toggle::after {
          display: none;
        }
        .dropdown-menu {
          border: none;
          border-radius: 0;
          margin: 0;
          padding: 0;
          position: fixed;
          left: 0;
          right: 0;
          top: auto;
          width: 100%;
          .dropdown-menu-container {
            background-color: #9e0000;
            padding: 0;

            .dropdown-item {
              color: white;
              font-size: 15px;
              line-height: 1.733;

              &:hover {
                color: #daa3a3;
                background-color: transparent;
              }

            }
          }
        }
      }
    }
  }
}





</style>
