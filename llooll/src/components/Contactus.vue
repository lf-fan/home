<template>
  <div class="contactus1">
    <el-button type="text" @click="dialogVisible = true">联系</el-button>

    <el-dialog
      title="登记"
      :visible.sync="dialogVisible"
      width="30%"
      :before-close="handleClose"
    >
      <span>姓名:</span>
      <el-input v-model="input" placeholder="请输入姓名"></el-input>
      <span>电话:</span>
      <el-input v-model="input" placeholder="请输入电话"></el-input>
      <span>邮箱:</span>
      <el-input v-model="input" placeholder="请输入邮箱"></el-input>
      <span>公司:</span>
      <el-input v-model="input" placeholder="请输入您所在的公司"></el-input>
      <span>主题:</span>
      <el-input v-model="input" placeholder="请输入主题"></el-input>
      <span>您的问题:</span>
      <el-input v-model="input" placeholder="请输入您的问题"></el-input>
      <el-button type="primary">提交</el-button>
      <span slot="footer" class="dialog-footer">
        <!-- <el-button @click="dialogVisible = false">取 消</el-button> -->
        <el-button type="primary" @click="dialogVisible = false"
          >关 闭</el-button
        >
      </span>
    </el-dialog>
  </div>
</template>

<script>
export default {
  data() {
    return {
      dialogVisible: false,
    };
  },
  methods: {
    // handleClose(done) {
    //   this.$confirm("确认关闭？")
    //     .then((_) => {
    //       done();
    //     })
    //     .catch((_) => {});
    // },
  },
};
</script>

<style scoped>
.contactus1 {
  height: 900px;
  width: 100%;
  border: 1px solid;
}
</style>