<template>
   <el-container>
      <el-header>客户管理系统</el-header>
      <el-container>
        <el-aside width="250px">
            <el-row class="tac">
              <el-col :span="24">
                <el-menu
                  router
                  default-active="2"
                  class="el-menu-vertical-demo"
                  @open="handleOpen"
                  @close="handleClose"
                  background-color="#545c64"
                  text-color="#fff"
                  active-text-color="#ffd04b">
                  <el-submenu index="1">
                    <template slot="title">
                      <i class="el-icon-menu"></i>
                      <span>客户管理</span>
                    </template>
                    <el-menu-item-group>
                      <el-menu-item index="/customer">客户资料</el-menu-item>
                      <el-menu-item index="1-2">充值管理</el-menu-item>
                      <el-menu-item index="1-3">补色管理</el-menu-item>
                      <el-menu-item index="1-4">预约管理</el-menu-item>
                    </el-menu-item-group>
                  </el-submenu>
                  <el-menu-item index="2">
                    <i class="el-icon-menu"></i>
                    <span slot="title">库存管理</span>
                  </el-menu-item>
                  <el-menu-item index="3">
                    <i class="el-icon-menu"></i>
                    <span slot="title">财务统计</span>
                  </el-menu-item>
                  <el-menu-item index="4">
                    <i class="el-icon-menu"></i>
                    <span slot="title">系统设置</span>
                  </el-menu-item>
                </el-menu>
              </el-col>
            </el-row>
        </el-aside>
        <el-container>
          <el-main>
              <router-view/>
          </el-main>
          <el-footer>
              版权@妍浠美妆 V1.0
          </el-footer>
        </el-container>
      </el-container>
    </el-container>
</template>

<script>
export default {
  name: 'app',
  methods:{
      handleOpen(key, keyPath) {
//        console.log(key, keyPath);
      },
      handleClose(key, keyPath) {
//        console.log(key, keyPath);
      }
}
}
</script>

<style scoped="true">
  .el-header, .el-footer {
    background-color: #B3C0D1;
    color: #333;
    text-align: center;
    line-height: 60px;
  }
  
  .el-aside {
    background-color: #D3DCE6;
    color: #333;
    text-align: center;
    line-height: 200px;
  }
  
  .el-main {
    background-color: #E9EEF3;
    color: #333;
    text-align: center;
/*    line-height: 720px;*/
  }
  
  body > .el-container {
    margin-bottom: 40px;
    height: 800px;
  }
  
  .el-container:nth-child(5) .el-aside,
  .el-container:nth-child(6) .el-aside {
    line-height: 260px;
  }
  
  .el-container:nth-child(7) .el-aside {
    line-height: 320px;
  }

</style>
