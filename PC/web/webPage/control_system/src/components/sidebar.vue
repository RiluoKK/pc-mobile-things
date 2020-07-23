<template>
  <div id="sidebar" class="sidebar">
    <h5>自定义颜色</h5>
    <el-menu
      default-active="1"
      class="sidebarC"
      @open="handleOpen"
      @close="handleClose"
      background-color="#545c64"
      text-color="#ffffff"
      active-text-color="#ffd04b"
      :router="true"
    >
      <el-submenu v-for="v in menu" :key="v.index" :index="v.index">
        <template slot="title">
          <i class="el-icon-location"></i>
          <span>{{v.title}}</span>
        </template>
        <el-menu-item-group>
          <template slot="title"></template>
          <el-menu-item v-for="j in v.childList" :key="j.index" :index="j.link" :route="j.link">{{j.title}}</el-menu-item>
        </el-menu-item-group>
      </el-submenu>
    </el-menu>
  </div>
</template>

<script>
// import
export default {
  data() {
    return {
      menu: [
        {
          index: "1",
          title: "管理菜单1",
          link: "/menu1",
          childList: [
            {
              index: "1-1",
              title: "管理菜单1子菜单1",
              link: "/menu1/meun1-1",
            },
          ],
        },
        {
          index: "2",
          title: "管理菜单2",
          link: "/menu2",
          childList: [
            {
              index: "2-1",
              title: "管理菜单2子菜单1",
              link: "/menu2/meun2-1",
            },
          ],
        },
      ],
    };
  },
  methods: {
    handleOpen(key, keyPath) {
      console.log(key, keyPath);
    },
    handleClose(key, keyPath) {
      console.log(key, keyPath);
    },
  },
};
</script>

<style lang="less">
.sidebar {
  display: flex;
  flex-direction: column;
  width: 200px;
  text-align: left;
  background: rgb(84, 92, 100);
  .sidebarC{
      flex:1;
      background: rgb(84, 92, 100);
  }
}
#sidebar{

h5 {
  padding: 20px 0 !important;
  text-align: center;
  font-size: 14px;
  color: #ffffff;
  margin-top: 10px;
  font-size: 18px;
}
.el-menu{
    border-right-width: 0 !important;
}
}

</style>