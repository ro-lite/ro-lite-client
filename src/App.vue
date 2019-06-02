<template>
  <div>
    <div>
      <mu-appbar style="width: 100%;" color="primary">
        <mu-button icon slot="left" @click.native="goBack">
          <mu-icon value="arrow_back"></mu-icon>
        </mu-button>仙境传说Ro Lite (同人)
        <mu-button icon slot="right" to="/search">
          <mu-icon value="search"></mu-icon>
        </mu-button>
      </mu-appbar>
    </div>
    <div>
      <router-view class="compoment" style="width: 100%;padding: 0px"/>
    </div>
    <div>
      <mu-flex style="width: 100%;" class="bottom-bar">
        <mu-container style="width: 100%;padding: 0px">
          <mu-bottom-nav color="primary" >
            <mu-bottom-nav-item title="任务" icon="home" to="/"></mu-bottom-nav-item>
            <mu-bottom-nav-item title="打怪" icon="trending_up" to="/stocks"></mu-bottom-nav-item>
            <mu-bottom-nav-item title="公会" icon="trending_up" to="/stocks"></mu-bottom-nav-item>
            <mu-bottom-nav-item title="我的" icon="trending_up" to="/stocks"></mu-bottom-nav-item>
          </mu-bottom-nav>
        </mu-container>
      </mu-flex>
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {};
  },
  created() {
    try {
      document.body.removeChild(document.getElementById("loading"));
    } catch (e) {}
  },
  methods: {
    goBack() {
      this.$router.back(-1);
    },
    gotoRoute(path) {
      this.$router.push(path);
    }
  }
};
</script>

<style>
@import "https://cdn.bootcss.com/material-design-icons/3.0.1/iconfont/material-icons.css";
@import "https://fonts.googleapis.com/css?family=Roboto:300,400,500,700,400italic";
body {
  min-height: 100vh;
  display: flex;
  flex-direction: column;
}
.compoment {
  flex: auto;
  margin-bottom: 56px;
}
.bottom-bar {
  position: fixed;
  bottom: 0;
  left: 0;
  right: 0;
}
</style>
