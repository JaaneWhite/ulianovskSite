<template>
<div>
  <page-title-inner :page-title-text="pageTitleText" :page-title-link="pageTitleLink" />
</div>
</template>

<script>
import PageTitleInner from "@/components/PageTitleInner";
export default {
  name: "fundsType",
  components: {PageTitleInner},
  data() {
    return {
      pageTitleText: '1917-1921гг. Симбирская контора закупочно-распределительного пункта Всероссийского центрального союза потребительских обществ  г.Симбирск Симбирской губернии',
      pageTitleLink: {text:'Назад к путеводителю по фондам', link: 'funds'}

    }
  }
}
</script>

<style scoped>

</style>
