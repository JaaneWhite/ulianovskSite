<template>
<div>
  <page-title-inner :page-title-text="pageTitleText" :page-title-link="pageTitleLink"></page-title-inner>
  <b-container>
    <b-row class="breadcrumb-row">
      <bread-crumbs :bread-crumb-items="breadCrumbItems" />
    </b-row>
    <b-row class="main-content-row">
      <b-col cols="12" md="12" xl="3" class="case-path-col"></b-col>
      <b-col cols="12" md="12" xl="9" class="case-attributes-col">
      </b-col>
    </b-row>


  </b-container>
</div>
</template>

<script>
import PageTitleInner from "@/components/PageTitleInner";
import BreadCrumbs from "@/components/BreadCrumbs";
export default {
  name: "caseType",
  components: {BreadCrumbs, PageTitleInner},
  data() {
    return {
      pageTitleText: 'Циркуляры и приказы ВСНХ СССР, распоряжения  Центрального Управления лесной промышленности',
      pageTitleLink: {text: 'Назад на страницу описи', link: 'inventory'},
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
          text: 'Ф. Р-91 Оп. 3',
          to: 'inventory'
        },
        {
          text: 'Циркуляры и приказы ВСНХ СССР, распоряжения  Центрального Управления лесной промышленности',
          active: true
        }
      ],
    }
  }
}
</script>

<style scoped>

</style>
