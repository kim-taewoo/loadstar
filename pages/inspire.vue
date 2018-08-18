<template>
  <v-layout>
    <v-flex text-xs-center>
      <div class="wrapper">
        <div class="test">
          <div class="test-inner"></div>
          <div class="test-background"></div>
        </div>
        <div class="header">
          <h1>This is my Header section</h1>
          <p>가끔은 이렇게 일일이 만드는 게 오히려 더 빠를수도 있다.</p>
        </div>

        <intersect @enter="selected = i" v-for="(i, index) in 9" :key="index">
          <div class="content">
            <div class="content-item-padding">
              <div class="content-icon"></div>
              <div class="stem-padding">
                <div class="stem-padding-left"></div>
                <div class="stem-padding-right"></div>
              </div>
            </div>
            <div>
              <p>
                This was written by Kim-Taewoo
              </p>
              <p class="content-item" :class="{hidden: selected == i}">
                Lorem ipsum dolor sit amet conse? Quo repudiandae itaque fugit!
              </p>
            </div>
          </div>
        </intersect>

      </div>

      <div class="footer" style="padding: 120px; height:400px;width: 100%;position: relative;z-index: 1; background:#303030;">
        <p>Lorem ipsum dolor sit amet consectetur adipisicing elit. Fugiat quo ex cum reiciendis alias quas dolorem nam quidem ipsa
          deleniti rem incidunt, illum optio nulla assumenda id consequatur adipisci ipsum!</p>
      </div>
    </v-flex>
  </v-layout>
</template>

<script>
import intersect from "vue-intersect";
export default {
  components: {
    intersect
  },
  data() {
    return {
      selected: null
    };
  }
};
</script>

<style scoped>
.hidden {
  opacity: 0;
}

.wrapper {
  position: relative;
}

.test {
  position: fixed;
  /* background-color: red; */
  width: 10px;
  /* height: 100%; */
  left: 50%;
  left: 60px;
  top: 0;
  bottom: 0;
}

.test-inner {
  position: absolute;
  top: 0;
  left: -30px;
  background-color: blue;
  width: 60px;
  height: 100%;
}

.test-background {
  position: absolute;
  top: 0;
  left: -30px;
  background-color: green;
  width: 60px;
  height: 50%;
}

.content {
  display: flex;
  width: 100%;
  justify-content: flex-start;
}

.content-item-padding {
  width: 90px;
  position: relative;
}

.stem-padding {
  position: absolute;
  top: 60px;
  right: 0;
  bottom: 0;
  width: 60px;
}

.stem-padding-left {
  width: 26px;
  float: left;
  background: #303030;
  position: relative;
  height: 100%;
}

.stem-padding-right {
  width: 26px;
  float: right;
  background: #303030;
  position: relative;
  height: 100%;
}

.content-icon {
  width: 60px;
  height: 60px;
  position: absolute;
  top: 0;
  right: 0;
  background: transparent no-repeat center center;
  background-size: cover;
  background-image: url(../assets/LifeSaver.png);
}

.content-item {
  /* max-width: 380px; */
  /* flex-grow: 1; */
  max-width: 80%;
  padding-left: 20px;
  padding-top: 15px;
  padding-bottom: 60px;
}

.header {
  position: relative;
  z-index: 1;
  background: green;
  height: 400px;
}

.header h1 {
  margin-top: 0;
}
</style>


