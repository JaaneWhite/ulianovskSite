<template>
  <div>
  <treeselect
    v-model="value"
    :multiple="true"
    :options="options"
    :defaultExpandLevel="1"
    :openDirection="bottom"
    class="funds-archive-filter" />



  </div>
 </template>


<script>
import Treeselect from '@riophae/vue-treeselect';
import '@riophae/vue-treeselect/dist/vue-treeselect.css';

export default {
  name: "AttrTree",
  components: {Treeselect},
  props: {
    options: {}
  }
}
</script>

<style scoped>
.funds-archive-filter {
  display: none;
}
</style>
