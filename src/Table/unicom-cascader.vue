<template>
  <el-cascader :options="dic"
               v-model="text"
               :placeholder="placeholder?placeholder:`请选择${label}`"
               :props="props"
               :clearable="clearable"
               :expand-trigger="expandTrigger"
               :show-all-levels="showAllLevels"
               :filterable="filterable"
               :separator="separator"
               :disabled="disabled"
               @change="handleChange">
  </el-cascader>
</template>

<script>
import unicomCompoents from './mixins/unicom-compoents.js'
export default {
  name: 'unicomCascader',
  mixins: [unicomCompoents()],
  props: {
    value: {
      type: Array,
      default: () => []
    },
    expandTrigger: {
      type: String,
      default: 'hover'
    },
    showAllLevels: {
      type: Boolean,
      default: true
    },
    filterable: {
      type: Boolean,
      default: false
    },
    separator: {
      type: String,
      default: '/'
    }
  },
  data () {
    return {}
  },
  watch: {},
  created () { },
  mounted () { },
  methods: {
    handleChange (value) {
      this.$emit('input', value)
    }
  }
}
</script>

<style>
</style>
