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

<style lang="scss">
/* по умолчанию -  мобильная версия - 0 - 767 px*/
@media (min-width: 0) {
  .pagination {
    margin: 10px auto;
  }
  .page-item.disabled .page-link, .page-item .page-link, .page-item:hover .page-link {
    color: #474435;
    background-color: transparent;
    font-size: 14px;
    line-height: 1.2 !important;
    box-shadow: none;
    border: none;
  }

  .page-item.active .page-link {
    color: #474435;
    background-color: #edeadb;
    border: none;
    font-size: 14px;
    line-height: 1.2;
    box-shadow: none;
  }
  .pagination-next-button {
    background-image: url("~assets/img/arrow right d.png");
    background-repeat: no-repeat;
    background-position: center;
  }
  .pagination-prev-button {
    background-image: url("~assets/img/arrow left.png");
    background-repeat: no-repeat;
    background-position: center;
  }

}


</style>
