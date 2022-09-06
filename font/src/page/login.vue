<template>
  <div>
    <div class="background">
      <div class="box_big pattern1">
        <div class="image1">
          <img src="" alt="找不到图片哦">

        </div>
        <div class="font1">
          <div class="font2">

          </div>
          <div class="font2 font2_pattern">

          </div>
        </div>

      </div>
      <div class="box_big pattern2">
        <div class="head">

        </div>
        <div class="login">

        </div>

      </div>

    </div>
  </div>
</template>

<script>
export default {
  name: "login"
}
</script>

<style scoped lang="css">
  .background {
    position: relative;
    left: 50%;
    margin-left: -720px;
    width: 1440px;
    height: 722px;
    background-color: pink;
  }
  .box_big {
    float: left;
    width: 720px;
    height: 722px;
  }
  .pattern1 {
    background-color: turquoise;
  }
  .pattern2 {
    background-color: aqua;
  }
  .box_big .image1 {
    position: absolute;
    top: 210px;
    left: 166px;
    width: 300px;
    height: 300px;
    background-color: white;
  }
  .box_big .font1 {
    position: absolute;
    top: 163px;
    left: 536px;
    width: 140px;
    height: 394px;
    background-color: cornflowerblue;
  }
  .font1 .font2 {
    float: left;
    width: 70px;
    height: 287px;
    background-color: white;
  }
  .font1 .font2_pattern {
    margin-top: 107px;
  }
  .box_big .login {
    position: absolute;
    top: 98px;
    left: 763px;
    width: 361px;
    height: 522px;
    background-color: cornflowerblue;
  }
  .box_big .head {
    position: absolute;
    top: 26px;
    left: 838px;
    width: 213px;
    height: 60px;
    background-color: indianred;
  }

</style>