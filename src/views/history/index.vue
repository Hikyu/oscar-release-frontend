<template>
  <div class="app-container">
    <el-tabs v-model="activeName" @tab-click="handleClick">
      <el-tab-pane label="正式版本" name="first">
        <official/>
      </el-tab-pane> 
      <el-tab-pane label="临时版本" name="second">
        临时版本
      </el-tab-pane>
    </el-tabs> 
  </div>
</template>

<script>
import Official from "./components/Official";

export default {
  components: {
    Official
  },
  data() {
    return {
      activeName: "second"
    };
  },
  methods: {
    handleClick(tab, event) {
      console.log(tab, event);
    }
  }
};
</script>

<style rel="stylesheet/scss" lang="scss" scoped>
.dashboard {
  &-container {
    margin: 30px;
  }
  &-text {
    font-size: 30px;
    line-height: 46px;
  }
}
</style>
