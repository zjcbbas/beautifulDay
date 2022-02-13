<template>
  <fieldset>
    <legend>射频配置:</legend>
    <el-form-item label="频段">
      <el-select v-model="form.region" placeholder="请选择频段">
        <el-option label="GSM900" value="GSM900"></el-option>
        <el-option label="GSM1800" value="GSM1800"></el-option>
        <el-option label="GSM1900" value="GSM1900"></el-option>
      </el-select>
    </el-form-item>
    <el-form-item label="信道">
      <el-select v-model="form.region" placeholder="请选择信道">
        <el-option label="低" value="低"></el-option>
        <el-option label="中" value="中"></el-option>
        <el-option label="高" value="高"></el-option>
      </el-select>
    </el-form-item>
    <el-form-item label="调制方式">
      <el-select v-model="form.region" placeholder="请选择调制方式">
        <el-option label="方式1" value="方式1"></el-option>
        <el-option label="方式2" value="方式2"></el-option>
        <el-option label="方式3" value="方式3"></el-option>
      </el-select>
    </el-form-item>
    <el-form-item label="功率">
      <el-select v-model="form.region" placeholder="请选择功率">
        <el-option label="MAX" value="MAX"></el-option>
        <el-option label="MAX+1.5" value="MAX+1.5"></el-option>
      </el-select>
    </el-form-item>
    <el-form-item label="主分集">
      <el-select v-model="form.region" placeholder="请选择主分集">
        <el-option label="主集" value="主集"></el-option>
        <el-option label="分集" value="分集"></el-option>
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
