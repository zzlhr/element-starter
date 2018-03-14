<template>
  <div id="app">

    <el-container>
      <el-header>
          <el-menu
                  :default-active="activeIndex2"
                  class="el-menu-demo"
                  mode="horizontal"
                  @select="handleSelect"
                  background-color="#545c64"
                  text-color="#fff"
                  active-text-color="#ffd04b">
              <el-menu-item index="1">砼鑫软件后台管理框架</el-menu-item>
              <el-submenu index="2">
                  <template slot="title">我的工作台</template>
                  <el-menu-item index="2-1">选项1</el-menu-item>
                  <el-menu-item index="2-2">选项2</el-menu-item>
                  <el-menu-item index="2-3">选项3</el-menu-item>
                  <el-submenu index="2-4">
                      <template slot="title">选项4</template>
                      <el-menu-item index="2-4-1">选项1</el-menu-item>
                      <el-menu-item index="2-4-2">选项2</el-menu-item>
                      <el-menu-item index="2-4-3">选项3</el-menu-item>
                  </el-submenu>
              </el-submenu>
              <el-menu-item index="3" disabled>消息中心</el-menu-item>
              <el-menu-item index="4"><a href="#" target="_blank">订单管理</a></el-menu-item>
          </el-menu>
      </el-header>
      <el-container>
        <el-aside width="202px">
            <el-col :span="24">
                <el-menu
                        default-active="2"
                        class="el-menu-vertical-demo"
                        @open="handleOpen"
                        @close="handleClose"
                        background-color="#545c64"
                        text-color="#fff"
                        active-text-color="#ffd04b" unique-opened router>
                    <el-submenu index="1">
                        <template slot="title">
                            <i class="el-icon-location"></i>
                            <span>{{classify}}</span>
                        </template>
                        <el-menu-item index="./pages/menu">菜单列表</el-menu-item>
                        <el-menu-item index="1-2">选项2</el-menu-item>
                        <!--<el-menu-item-group>-->
                            <!--&lt;!&ndash;<template slot="title">菜单管理</template>&ndash;&gt;-->
                            <!--<el-menu-item index="1-1">选项1</el-menu-item>-->
                            <!--<el-menu-item index="1-2">选项2</el-menu-item>-->
                        <!--</el-menu-item-group>-->
                        <!--<el-menu-item-group title="分组2">-->
                            <!--<el-menu-item index="1-3">选项3</el-menu-item>-->
                        <!--</el-menu-item-group>-->
                        <!--<el-submenu index="1-4">-->
                            <!--<template slot="title">选项4</template>-->
                            <!--<el-menu-item index="1-4-1">选项1</el-menu-item>-->
                        <!--</el-submenu>-->
                    </el-submenu>
                    <el-menu-item index="2">
                        <i class="el-icon-menu"></i>
                        <span slot="title">导航二</span>
                    </el-menu-item>
                    <el-menu-item index="3" disabled>
                        <i class="el-icon-document"></i>
                        <span slot="title">导航三</span>
                    </el-menu-item>
                    <el-menu-item index="4">
                        <i class="el-icon-setting"></i>
                        <span slot="title">导航四</span>
                    </el-menu-item>
                </el-menu>
            </el-col>

        </el-aside>
        <el-container>
          <el-main>
            <img src="./assets/logo.png">
            <div>
              <el-button @click="startHacking">Start</el-button>
            </div>

          </el-main>
          <el-footer>Footer</el-footer>
        </el-container>
      </el-container>
    </el-container>

  </div>
</template>

<script>
export default {
    data() {
        return {
            classify: '系统设置',
        }
    },
    methods: {
        startHacking () {
          this.$notify({
            title: 'It works!',
            type: 'success',
            message: 'We\'ve laid the ground work for you. It\'s time for you to build something epic!',
            duration: 5000
          })
        },
        handleOpen(key, keyPath) {
            console.log(key, keyPath);
        },
        handleClose(key, keyPath) {
            console.log(key, keyPath);
        },
        computed:{
            onRoutes (){
                return this.$route.path.replace('/','')
            }
        }

    }
}
</script>

<style>
    #app {
        font-family: Helvetica, sans-serif;
        text-align: center;
        height: 100%;
    }
    .el-container{
        height: 100%;
    }
    .el-header{
        padding: 0;
    }
    .el-menu{
        border-bottom-color: #535C63;
        border-right: solid 0 #e6e6e6;

    }
    .el-aside{
        background-color: #535C63;
    }
</style>
