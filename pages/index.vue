<template>
<b-row class="main-row">
  <b-container>
  <b-row class="search-row">
    <SearchTabs/>
  </b-row>
  <b-row class="pop-sections">

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
}
}
@media (min-width: 1024px) {
  .search-row {

  }


}
</style>
