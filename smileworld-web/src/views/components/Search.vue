<template>
  <div id="search">
    <IForm inline :model="model" :elem="elem" :loading="loading" :btn-loading="btnLoading" :label-width="labelWidth" @on-submit="handleSearch" @on-reset="handleReset" :btn-label-width="4" reset submit-text="查询" ok-icon="md-search" btn-icon="md-refresh">
      <slot slot="head" name="head"> </slot>
      <slot> </slot>
      <slot slot="button" name="button"> </slot>
    </IForm>
    <!-- IForm -->
  </div>
</template>
<script>
export default {
  name: 'Search',
  props: {
    model: Object,
    elem: Array,
    loading: Boolean,
    btnLoading: Boolean,
    labelWidth: Number
  },
  data: () => ({

  }),
  methods: {
    handleReset() {
      this.$emit('on-search', 'reset')
    },
    handleSearch() {
      this.$emit('on-search', 'search')
    }
  }
}
</script>
<style lang="postcss">
#search .ivu-form-item {
  margin-bottom: 8px;
}
</style>
