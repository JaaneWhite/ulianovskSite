<template>
<page-title :page-title-text="pageTitleText"></page-title>
</template>

<script>
import PageTitle from "@/components/PageTitle";
export default {
  name: "funds",
  components: {PageTitle},
  data() {
    return {
      pageTitleText: 'Путеводитель по фондам досоветского периода'
    }
  }
}
</script>

<style scoped>

</style>
