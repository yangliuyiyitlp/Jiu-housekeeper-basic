<template>
  <div id="NavBar">
    <el-menu theme="dark" :default-active="activeIndex" class="el-menu-demo" mode="horizontal" @select="handleSelect">
      <li data-v-01c7fadb class="img"><img class='Mainimg' src="../images/99.png" alt=""></li>
      <!--<el-menu-item index="1" @click="mypanel">我的面板</el-menu-item>-->
      <li data-v-01c7fadb class="img">赳赳管家</li>
      <el-menu-item index="3" @click="mypanel">系统设置</el-menu-item>
      <el-menu-item index="4">设备管理</el-menu-item>
      <el-menu-item index="5">内容管理</el-menu-item>
      <el-menu-item index="6">状态监控</el-menu-item>
      <el-menu-item index="7">会员管理</el-menu-item>
      <el-menu-item index="8">报表统计</el-menu-item>
      <el-menu-item index="9">城市运营</el-menu-item>
      <el-menu-item index="10">客服管理</el-menu-item>
      <el-menu-item index="11">红包管理</el-menu-item>
      <el-menu-item index="12">活动中心</el-menu-item>
      <el-submenu index="13" class="right ">
        <template slot="title"><i class="iconfont icon-anonymity"></i>个人信息</template>
        <el-menu-item index="2-1" class="user" @click="userinfo">个人信息</el-menu-item>
        <el-menu-item index="2-2" class="user">修改密码</el-menu-item>
      </el-submenu>
      <li data-v-01c7fadb class="time right">{{date | convertDate}}</li>
    </el-menu>
  </div>
</template>

<script>

  export default {
    data () {
      return {
        activeIndex: '1',
        date: new Date()
      }
    },
    methods: {
      handleSelect (key, keyPath) {
        console.log(key, keyPath)
      },
      // 跳转到我的面板页面
      userinfo () {
        this.$router.push({
          name: 'Userinfo'
        })
      },
      mypanel () {
        this.$router.push({
          name: 'Mypanel'
        })
      }
    }
  }
</script>
<style scoped>
  .img {
    float: left;
    margin: 0;
    position: relative;
    box-sizing: border-box;
    color: #bfcbd9;
    font-size: 0.8rem;
    height: 60px;
    line-height: 60px;
  }

  .Mainimg {
    height: 60px !important;
  }

  li {
    font-size: 0.5rem;
    font-family: Arial, "Microsoft YaHei";
    padding: 0.5rem;
  }

  .icon-anonymity {
    font-size: 14px !important;
  }

  .right {
    float: right;
  }

  .time {
    float: right;
    height: 60px;
    line-height: 60px;
    margin: 0;
    position: relative;
    box-sizing: border-box;
    color: #bfcbd9;
    margin-right: -40px;
    font-size: 14px;
  }

  .user {
    background-color: #eef1f6 !important;
    padding: 0 !important;
    width: 0px !important;
    margin: 0px;
    font-size: 14px !important;
  }

</style>
