<template>
  <div id="app">
 <div id="header">aa</div>
 <div id="menu">123</div>
  <div class="level1">1
    <div class="level1 level2">2
      <div class="level1 level2 level3">3</div>
    </div>
  </div>
  <p class="clearfix">4</p>
  <div class="component">规则嵌套和冒泡</div>
<el-checkbox-group v-model="viewData.checkList">
    <el-checkbox style="margin:5px" name="requiredType"
     @change="(value)=>checkChange(value,'siteRequired')"
     label="siteRequired">站内信</el-checkbox>
asas
 <el-checkbox  style="margin:5px" name="requiredType"
 @change="(value)=>checkChange(value,'smsRequired')"
   label="smsRequired">短信</el-checkbox>
</el-checkbox-group>
          <router-link :to="{ name: 'test' }" title="test">
          产看 test 页面
          </router-link>
    <!-- <el-input v-model="obj.name" placeholder=""></el-input> -->
        <el-input v-model="obj2.age" placeholder=""></el-input>
    <el-button  @click="freeze"> 冻结</el-button>

    {{obj.name}}
    {{obj2.age}}
    <img src="./assets/logo.png">
    <router-view/>
  </div>
</template>
<script>
let da = {age: 1}

export default {
  name: 'App',
  created () {
    console.log(process.env)
  },
  data: function () {
    return {
      viewData: {
        checkList: []
      },
      // obj: Object.freeze({name: 'aa'})
      obj: {name: 'aa'},
      obj2: da
    }
  },
  methods: {
    freeze () {
      // alert()
      this.obj = Object.freeze({name: 'cc'})
      // Object.freeze(this.name)
    },
    checkChange () {
      console.log(this.viewData)
    }
  }
}
</script>
<style lang="less">
/*
/使用 变量 less 必须使用冒号结束
*/
@var:10px;
#header {
  width:@var
}
/*
/ 使用混合mixins
 */
.border-top{
  border-top: 1px  solid red;
}
#border-bottom{
  border-bottom: 1px solid silver;
}
#menu{
 .border-top();
 #border-bottom()
}
/*
/ 使用嵌套
 */
.level1{
  border-top:1px solid red;
.level2{
    border-bottom:1px solid red;
    .level3{
      border-left: 1px solid red;

    }
}
}

/*
/ 使用 伪元素 混合
 */
.clearfix {
  display: block;
  zoom: 1;

  &:after {
    content: "aaa4"
  }
}
/*
/ 使用  条件 显示不同的样式 ， 浏览器宽度 大于  768px  小于 1280px 则显示  600，大于 1280px 显示800px
 */
.component {
  border:1px solid red;
  width: 300px;
  @media (min-width: 768px) {
    width: 600px;
    @media  (min-resolution: 192dpi) {
      background-image: url(/img/retina2x.png);
    }
  }
  @media (min-width: 1280px) {
    width: 800px;
  }
}
</style>
<style>
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
