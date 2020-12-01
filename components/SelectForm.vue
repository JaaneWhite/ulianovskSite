<template>
  <b-form-select
    v-model="selected"
    :options="options"
    class="form-select"
    @change="onSelectChanges()"
  >

  </b-form-select>
</template>

<script>
export default {
  name: "SelectForm",
  props: {
    selected: {},
    options: {}
  },
  methods: {
    onSelectChanges: function () {
      this.$emit("selectChanged", this.selected)
    }
  }
}
</script>

<style lang="scss">
/* по умолчанию -  мобильная версия - 0 - 767 px*/
@media (min-width: 0) {
  .custom-select {
    width: auto;
    height: 100%;
    font-size: 14px;
    font-weight: bold;
    border-radius: 0;
    border: none;
    padding: 0;
    padding-right: 10px;
    padding-left: 10px;
    background: url("~assets/svg/arrow down.svg") no-repeat right;
    background-size: 10px;
    box-shadow: none;
    color: #474334;

    &:hover, &:focus, &:active {
      box-shadow: none;
      border: none;
    }
  }
}


</style>
