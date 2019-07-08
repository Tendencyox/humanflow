<template>
    <el-container style="height: 95%; border: 10px solid #eee">
    <el-aside width="12%" style="background-color: rgb(238, 241, 246)">
        <el-menu :default-openeds="['1', '3']">
        <el-submenu index="1">
            <template slot="title"><i class="el-icon-message"></i>信息</template>
            <el-menu-item-group>
            <template slot="title">汇总信息</template>
            <el-menu-item index="1-1">基本信息</el-menu-item>
            <!-- <el-menu-item index="1-2">选项2</el-menu-item> -->
            </el-menu-item-group>
        </el-submenu>
        <el-submenu index="2">
            <template slot="title"><i class="el-icon-menu"></i>视频</template>
            <el-menu-item-group>
            <template slot="title">分组一</template>
            <el-menu-item v-on:click='toPage2' index="2-1">实时情况</el-menu-item>
            <!-- <el-menu-item index="2-2"></el-menu-item> -->
            </el-menu-item-group>
            <el-menu-item-group title="分组2">`
            <el-menu-item index="2-3">人流预测</el-menu-item>
            </el-menu-item-group>
        </el-submenu>
        <el-submenu index="3">
            <template slot="title"><i class="el-icon-setting"></i>个人中心</template>
            <el-menu-item-group>
            <template slot="title">分组一</template>
            <el-menu-item index="3-1">权限管理</el-menu-item>
            <el-menu-item index="3-2">个人中心</el-menu-item>
            </el-menu-item-group>
        </el-submenu>
        </el-menu>
    </el-aside>
  
  <el-container>
    <el-header style="text-align: right; font-size: 150%">
      <el-dropdown>
        <i class="el-icon-setting" style="margin-right: 150%"></i>
        <el-dropdown-menu slot="dropdown">
          <el-dropdown-item>查看</el-dropdown-item>
          <el-dropdown-item>新增</el-dropdown-item>
          <el-dropdown-item>删除</el-dropdown-item>
        </el-dropdown-menu>
      </el-dropdown>
      <span>admin</span>
    </el-header>
    
    <el-main>
      <el-table :data="tableData">
        <el-table-column prop="date" label="日期" width="200%">
        </el-table-column>
        <el-table-column prop="id" label="设备唯一id" width="200%">
        </el-table-column>
        <el-table-column prop="address" label="地址信息" width="200%">
        </el-table-column>
        <el-table-column prop="threshold" label="上传时阈值（人头数）" width="200%">
        </el-table-column>
        <el-table-column prop="duration" label="超过阈值时长(s)" width="200%">
        </el-table-column>
        <el-table-column prop="right" label="操作" width="200%">
            <template>
                <!-- <el-button type="primary" @click="playVideo(scope,row)" ref="btn" size="small">播放</el-button> -->
                <el-button type="primary" @click="playpage" ref="btn" size="small">修改</el-button>
                <el-button type="text" @click="video_delete" size="small">删除</el-button>
            </template>
        </el-table-column>
      </el-table>
    </el-main>
  </el-container>
</el-container>
</template>


<style>
  .el-header {
    background-color: #B3C0D1;
    color: #333;
    line-height: 60px;
  }
  
  .el-aside {
    color: #333;
  }
</style>

<script>
  export default {
    data() {
      return {
        tableData: [{
            date: '2016-05-02',
            id: '0x01',
            address: '江苏省南京市 江宁-南航-主楼',
            threshold: 5,
            duration: 25
          }, {
            date: '2016-05-04',
            id: '0x02',
            address: '江苏省南京市 江宁-南航-北大门',
            threshold: 5,
            duration: 18
          }, {
            date: '2016-05-01',
            id: '0x01',
            address: '江苏省南京市 江宁-南航-主楼',
            threshold: 5,
            duration: 105
          }, {
            date: '2016-05-03',
            id: '0x04',
            address: '江苏省南京市 江宁-托乐嘉-苏果',
            threshold: 5,
            duration: 59
          }]
      }
    },
    method: {
      toPage2(done) {
        console.log('to page 2')
        this.$router.push({path:'page2'})
      },
      playpage(){},
      video_delete(){},
    }
  };
</script>