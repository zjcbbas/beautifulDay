<template>
  <fieldset>
    <legend>射频配置:</legend>
    <el-form-item label="带宽">
      <el-select v-model="form.region" placeholder="请选择带宽">
        <el-option label="GSM900" value="GSM900"></el-option>
        <el-option label="GSM1800" value="GSM1800"></el-option>
        <el-option label="GSM1900" value="GSM1900"></el-option>
      </el-select>
    </el-form-item>
  </fieldset>
</template>

<script>
    export default {
      name: "MyChild",
      data() {
        return {
          form: {
            name: '',
            region: '',
            date1: '',
            date2: '',
            delivery: false,
            type: [],
            resource: '',
            desc: ''
          },
        }
      },
      props: {
        parentMessage: {
          type: String,
          default: '默认显示的信息'
          // require: true // 必填
        }
      }
    }
</script>

<style scoped>

</style>
