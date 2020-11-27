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
import SearchTabs from "~/pages/SearchTabs";

export default {
  components: {SearchTabs}
}
</script>

<style lang="scss">
/* по умолчанию -  мобильная версия - 0 - 767 px*/
@media (min-width: 0) {
  .main-row {
    background-image: url("~assets/img/bg.png");
  }
}
@media (min-width: 768px) {

}
@media (min-width: 1024px) {


}
</style>
