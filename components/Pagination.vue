<template>
  <b-pagination
    v-model="currentPage"
    :total-rows="totalRows"
    :per-page="perPage"
    :aria-controls="paginationAreaControls"
    pills
    first-number
    last-number
    class="pagination"
    next-text=""
    next-class="pagination-next-button"
    prev-text=""
    prev-class="pagination-prev-button"
  ></b-pagination>
</template>

<script>
export default {
  name: "Pagination",
  data() {
    return {
      currentPage: 1
    }
  },
  props: {
    totalRows: {},
    paginationAreaControls: {},
    perPage: {}
  }
}
</script>

<style scoped>

</style>
