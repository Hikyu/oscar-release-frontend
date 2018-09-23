<template>
  <div class="createPost-container">
    <el-form ref="form" :model="form" label-width="120px">
      <sticky>
        <el-button v-loading="loading" style="margin-left: 10px;" type="success" >构建</el-button>
        <el-button v-loading="loading" type="warning">设为模板</el-button>
      </sticky>
      <div class="createPost-main-container ">
        <el-form-item label="Activity name">
          <el-input v-model="form.name"/>
        </el-form-item>
        <el-form-item label="Activity zone">
          <el-select v-model="form.region" placeholder="please select your zone">
            <el-option label="Zone one" value="shanghai"/>
            <el-option label="Zone two" value="beijing"/>
          </el-select>
        </el-form-item>
        <el-form-item label="Activity time">
          <el-col :span="11">
            <el-date-picker v-model="form.date1" type="date" placeholder="Pick a date" style="width: 100%;"/>
          </el-col>
          <el-col :span="2" class="line">-</el-col>
          <el-col :span="11">
            <el-time-picker v-model="form.date2" type="fixed-time" placeholder="Pick a time" style="width: 100%;"/>
          </el-col>
        </el-form-item>
        <el-form-item label="Instant delivery">
          <el-switch v-model="form.delivery"/>
        </el-form-item>
        <el-form-item label="Activity type">
          <el-checkbox-group v-model="form.type">
            <el-checkbox label="Online activities" name="type"/>
            <el-checkbox label="Promotion activities" name="type"/>
            <el-checkbox label="Offline activities" name="type"/>
            <el-checkbox label="Simple brand exposure" name="type"/>
          </el-checkbox-group>
        </el-form-item>
        <el-form-item label="Resources">
          <el-radio-group v-model="form.resource">
            <el-radio label="Sponsor"/>
            <el-radio label="Venue"/>
          </el-radio-group>
        </el-form-item>
        <el-form-item label="Activity form">
          <el-input v-model="form.desc" type="textarea"/>
        </el-form-item>
        <el-form-item>
          <el-button type="primary" @click="onSubmit">Create</el-button>
          <el-button @click="onCancel">Cancel</el-button>
        </el-form-item>
        <el-steps :active="2"  align-center finish-status="success">
          <el-step title="生成发布单"></el-step>
          <el-step title="填写发布单"></el-step>
          <el-step title="开始构建"></el-step>
        </el-steps>
      </div>
    </el-form>
    
  </div>
</template>

<script>
import Sticky from "@/components/Sticky"; // 粘性header组件

export default {
  components: { Sticky },
  data() {
    return {
      form: {
        name: "",
        region: "",
        date1: "",
        date2: "",
        delivery: false,
        type: [],
        resource: "",
        desc: ""
      }
    };
  },
  methods: {
    onSubmit() {
      this.$message("submit!");
    },
    onCancel() {
      this.$message({
        message: "cancel!",
        type: "warning"
      });
    }
  }
};
</script>

<style rel="stylesheet/scss" lang="scss" scoped>
.line {
  text-align: center;
}
.createPost-container {
  position: relative;
  .createPost-main-container {
    padding: 40px 45px 20px 50px;
  }
}
</style>

