<template>
<div>
  <page-title :page-title-text="pageTitleText"></page-title>
  <b-container>
    <b-row class="breadcrumb-row">
      <bread-crumbs :bread-crumb-items="breadCrumbItems"></bread-crumbs>

    </b-row>

  </b-container>
</div>
</template>

<script>
import PageTitle from "@/components/PageTitle";
import BreadCrumbs from "@/components/BreadCrumbs";
export default {
  name: "funds",
  components: {BreadCrumbs, PageTitle},
  data() {
    return {
      pageTitleText: 'Путеводитель по фондам досоветского периода',
      breadCrumbItems: [
        {
          text: 'Главная',
          to: '/'
        },
        {
          text: 'Путеводители – Путеводитель по фондам досоветского периода',
          active: true
        }
      ],
    }
  }
}
</script>

<style scoped>

</style>
