<template>
  <div>
    <div class="main">
      <div class="slides">
        <ul>
          <li class="active"><a href="#"><img src="./assets/b_01.jpg" alt="第1张图的描述信息"></a></li>
          <li><a href="#"><img src="./assets/b_02.jpg" alt="第2张图的描述信息"></a></li>
          <li><a href="#"><img src="./assets/b_03.jpg" alt="第3张图的描述信息"></a></li>
          <li><a href="#"><img src="./assets/b_04.jpg" alt="第4张图的描述信息"></a></li>
          <li><a href="#"><img src="./assets/b_05.jpg" alt="第5张图的描述信息"></a></li>
          <li><a href="#"><img src="./assets/b_06.jpg" alt="第6张图的描述信息"></a></li>
          <li><a href="#"><img src="./assets/b_07.jpg" alt="第7张图的描述信息"></a></li>
          <li><a href="#"><img src="./assets/b_08.jpg" alt="第8张图的描述信息"></a></li>
          <li><a href="#"><img src="./assets/b_09.jpg" alt="第9张图的描述信息"></a></li>
          <li><a href="#"><img src="./assets/b_10.jpg" alt="第9张图的描述信息"></a></li>
        </ul>

        <div class="extra">
          <h3>第1张图的描述信息</h3>
          <a class="prev" href="javascript:;"></a>
          <a class="next" href="javascript:;"></a>
        </div>
      </div>
      <div class="indicator">
        <ul>
          <li class="active">
            <img src="./assets/s_01.jpg">
            <span class="mask"></span>
            <span class="border"></span>
          </li>
          <li>
            <img src="./assets/s_02.jpg">
            <span class="mask"></span>
            <span class="border"></span>
          </li>
          <li>
            <img src="./assets/s_03.jpg">
            <span class="mask"></span>
            <span class="border"></span>
          </li>
          <li>
            <img src="./assets/s_04.jpg">
            <span class="mask"></span>
            <span class="border"></span>
          </li>
          <li>
            <img src="./assets/s_05.jpg">
            <span class="mask"></span>
            <span class="border"></span>
          </li>
          <li>
            <img src="./assets/s_06.jpg">
            <span class="mask"></span>
            <span class="border"></span>
          </li>
          <li>
            <img src="./assets/s_07.jpg">
            <span class="mask"></span>
            <span class="border"></span>
          </li>
          <li>
            <img src="./assets/s_08.jpg">
            <span class="mask"></span>
            <span class="border"></span>
          </li>
          <li>
            <img src="./assets/s_09.jpg">
            <span class="mask"></span>
            <span class="border"></span>
          </li>
          <li>
            <img src="./assets/s_10.jpg">
            <span class="mask"></span>
            <span class="border"></span>
          </li>
        </ul>
      </div>
    </div>
  </div>
</template>

<script>
import lunbo from './lunbo.js';

export default {
  data() {
    return {
      i: 1
    }
  },
  mounted() {
    if (i = 1) {
      lunbo()
    }

    // console.log('111', lunbo);
  },

  beforeDestroy() {
    i = 0
  }

}
</script>
<style scoped>
* {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
}

li {
  list-style: none;
}

.main {
  width: 700px;
  margin: auto;
  background: #000;
}

.slides {
  height: 320px;
  position: relative;
}

.slides ul li {
  /* display: none; */
  position: absolute;
  top: 0;
  left: 0;
  opacity: 0;
  /* 这里实现淡入淡出的关键 */
  transition: all .3s;
}


.slides li.active {
  /* display: block; */
  opacity: 1;
}

.slides .extra {
  width: 700px;
  height: 53px;
  line-height: 53px;
  position: absolute;
  bottom: 0px;
  background-color: rgba(0, 0, 0, 0.8);
  z-index: 10;
}

.slides .extra h3 {
  width: 82%;
  margin: 0;
  margin-right: 20px;
  padding-left: 20px;
  color: #98E404;
  font-size: 28px;
  float: left;
  font-weight: 500;
  font-family: "Microsoft Yahei", Tahoma, Geneva;
}

.slides .extra a {
  width: 30px;
  height: 29px;
  display: block;
  float: left;
  margin-top: 12px;
  margin-right: 3px;
  background-image: url(./assets/icon_focus_switch.png);
}

.slides .extra .prev {
  background-position: 0 0;
}

.slides .extra .prev:hover {
  background-position: -30px 0;
}

.slides .extra .next {
  background-position: -60px 0;
}

.slides .extra .next:hover {
  background-position: -90px 0;
}

.indicator {
  padding: 10px 0;
}

.indicator ul {
  list-style-type: none;
  margin: 0 0 0 4px;
  padding: 0;
  overflow: hidden;
}

.indicator ul li {
  position: relative;
  float: left;
  width: 60px;
  margin: 0 4px 0 5px;
  text-align: center;

  cursor: pointer;
}

.indicator li img {
  display: block;
  border: 0;
  text-align: center;
  width: 60px;
}

.indicator li .mask {
  width: 60px;
  height: 60px;
  position: absolute;
  top: 0;
  left: 0;
  background-color: rgba(0, 0, 0, 0.4);
}

.indicator li .border {
  display: none;
  width: 54px;
  position: absolute;
  bottom: 0;
  left: 0;
  z-index: 20;
  border: 3px solid #98E404;
}

/* li里面的mask 和 border 刚开始都是显示的 */
/* 我们写一个样式css */
.indicator .active .mask {
  display: none;
}

.indicator .active .border {
  display: block;
}
</style>