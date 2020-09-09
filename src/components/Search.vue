<template>
  <div class="wrapper">
    <div class="search-box" :class="addShowClass" @mouseover="show()" @mouseleave="hide()">
      <form action="http://www.baidu.com/s" method="GET" id="myform">
        <input class="search-txt" type="text" name="wd" placeholder="Type to search" autocomplete="on" autofocus="autofocus">
        <a class="search-btn" style="cursor:pointer" onclick="document:myform.submit();">
          <i class="fas fa-search"></i>
        </a>
      </form>
    </div>
    <div class="bg"></div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      visible: false,
    };
  },
  methods: {
    show() {
      this.visible = true;
    },
    hide() {
      this.visible = false;
    },
  },
  computed: {
    addShowClass() {
      return { show: this.visible };
    },
  },
};
</script>

<style lang="css" scoped>
body {
  margin: 0px;
  padding: 0px;
}
.bg {
  position: absolute;
  top: 0;
  z-index: 0;
  margin: 0 auto;
  width: 100%;
  height: 100vh;
  background: url(https://blog.mrabit.com/bing/today) no-repeat center;

  background-size: cover;
  transition: 0.4s;
}
.search-box {
  z-index: 1;
  position: absolute;
  top: 47%;
  left: 50%;
  transform: translate(-50%, -50%);
  /* 以上代码是在不知道具体位置时水平垂直居中 */
  background: white;
  height: 33px;
  border-radius: 33px;
  padding: 10px;
  opacity: 70%;
}
.search-box.show {
  opacity: 90%;
}
/* 空格是后代选择器，>是子类选择器，使用>时不会选择子类的子类 */
.search-box.show .search-txt {
  width: 300px;
  padding: 0 6px;
}
.search-box.show .search-btn {
  background: #09f;
  color: white;
}
.search-box.show + .bg {
  /* -webkit-filter: blur(5px);
    -moz-filter: blur(5px);
    -o-filter: blur(5px);
    -ms-filter: blur(5px);
    filter: blur(5px); */
  filter: brightness(60%);
  -webkit-filter: brightness(50%);
}
.search-btn {
  color: #09f;
  float: right;
  width: 33px;
  height: 33px;
  border-radius: 50%;
  background: white;
  display: flex;
  justify-content: center;
  align-items: center;
  transition: 0.4s;
  text-decoration: none;
}
.search-txt {
  border: none;
  background: none;
  outline: none;
  float: left;
  padding: 0;
  color: gray;
  font-size: 16px;
  transition: 0.4s;
  line-height: 33px;
  width: 0;
}
</style>