<template>
  <div id="app">
<!--    <router-view />-->
    <el-row :gutter="24" style="padding:16px">

      <el-col :span="10">
        <el-form ref="form" :model="form" label-width="80px">
          <span style="text-align: center;display:block;font-size: 24px; padding-bottom: 14px;">信号配置A</span>
          <el-form-item label="信号制式">
            <el-select  @change="gmsChange" v-model="gmsValue" placeholder="请选择信号制式">
              <el-option label="GSM" value="GSM"></el-option>
              <el-option label="其他" value="Other"></el-option>
            </el-select>
          </el-form-item>
          <my-child-one v-if="gmsValue=='GSM'" :parentMessage="parentMessage"></my-child-one>
          <my-child-two v-if="gmsValue=='Other'" :parentMessage="parentMessage"></my-child-two>
          <el-form-item label="开关">
            <el-switch
              v-model="form.delivery"
              active-text="ON"
              inactive-color="#BFBFBF"
              inactive-text="OFF"
              active-value="1"
              inactive-value="0"/>
          </el-form-item>
          <!--<el-form-item>
            <el-button type="primary" @click="onSubmit">立即创建</el-button>
            <el-button>取消</el-button>
          </el-form-item>-->
        </el-form>
      </el-col>
      <el-col :span="10">
        <el-form ref="form" :model="form" label-width="80px">
          <span style="text-align: center;display:block;font-size: 24px; padding-bottom: 14px;">信号配置B</span>
          <el-form-item label="信号制式">
            <el-select  @change="gmsChange2" v-model="gmsValue2" placeholder="请选择信号制式">
              <el-option label="GSM" value="GSM"></el-option>
              <el-option label="其他" value="Other"></el-option>
            </el-select>
          </el-form-item>
          <my-child-one v-if="gmsValue2=='GSM'" :parentMessage="parentMessage"></my-child-one>
          <my-child-two v-if="gmsValue2=='Other'" :parentMessage="parentMessage"></my-child-two>
          <el-form-item label="开关">
            <el-switch
              v-model="form.delivery"
              active-text="ON"
              inactive-color="#BFBFBF"
              inactive-text="OFF"
              active-value="1"
              inactive-value="0"/>
          </el-form-item>
         <!-- <el-form-item>
            <el-button type="primary" @click="onSubmit">立即创建</el-button>
            <el-button>取消</el-button>
          </el-form-item>-->
        </el-form>
      </el-col>
      <el-col :span="20">
        <el-form ref="form" :model="form" label-width="80px" :inline="true">
          <fieldset>
            <legend>测试项目:</legend>
            <el-form-item label="项目名称">
              <el-input v-model="form.name"></el-input>
            </el-form-item>
            <el-form-item>
              <el-button type="primary">按钮1</el-button>
            </el-form-item>
            <el-form-item>
              <el-button type="success">按钮2</el-button>
            </el-form-item>
            <el-form-item>
              <el-button type="danger">按钮3</el-button>
            </el-form-item>
          </fieldset>
         <!-- <el-form-item>
            <el-button type="primary" @click="onSubmit">立即创建</el-button>
            <el-button>取消</el-button>
          </el-form-item>-->
        </el-form>
      </el-col>
      <el-col :span="20">
        <el-form ref="form" :model="form" label-width="80px" :inline="true">
          <fieldset>
            <legend>数据显示区域:</legend>
            <el-form-item label="参数1">
              <el-input v-model="form.name"></el-input>
            </el-form-item>
            <el-form-item label="参数2">
              <el-input v-model="form.name"></el-input>
            </el-form-item>
            <el-form-item label="参数3">
              <el-input v-model="form.name"></el-input>
            </el-form-item>
          </fieldset>
          <!-- <el-form-item>
             <el-button type="primary" @click="onSubmit">立即创建</el-button>
             <el-button>取消</el-button>
           </el-form-item>-->
        </el-form>
      </el-col>
    </el-row>
  </div>
</template>

<script>
  import MyChildOne from './MyChildOne'
  import MyChildTwo from './MyChildTwo'
export default  {
  name:  'App',
  components: {
    MyChildOne,
    MyChildTwo
  },
  data() {
    return {
      gmsValue: 'GSM',
      gmsValue2: 'Other',
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
      parentMessage: "我是来自父组件的消息"
    }
  },
  methods: {
    onSubmit() {
      console.log('submit!');
    },
    gmsChange(value) {
      console.log(value)
    },
    gmsChange2(value) {
      console.log(value)
    }
  }
}
</script>
