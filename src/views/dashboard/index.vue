<template>
<div class="mixin-components-container">
  <el-row :gutter="20">
      <el-card class="box-card">
        <div slot="header" class="clearfix">
          <span>待办事项</span>
        </div>
        <div style="margin-bottom:50px;">
           <el-col :span="6">
            <el-card class="box-card" style="margin-bottom:20px;">
              <div slot="header" class="clearfix">
                <span>发布单1</span>
              </div>
              <div style="height:100px;">
                Hello,World
              </div>
            </el-card>
          </el-col>
        </div>
      </el-card>
    </el-row>

    <el-row :gutter="20" style="margin-top:50px;">
      <el-card class="box-card">
        <div slot="header" class="clearfix">
          <span>我的发布</span>
        </div>
        <div style="margin-bottom:50px;">
           Hello,World
        </div>
      </el-card>
    </el-row>
</div>
</template>

<script>
import { mapGetters } from "vuex";

export default {
  name: "Dashboard",
  computed: {
    ...mapGetters(["name", "roles"])
  }
};
</script>

<style scoped>
.mixin-components-container {
  background-color: #f0f2f5;
  padding: 30px;
  min-height: calc(100vh - 84px);
}
</style>
