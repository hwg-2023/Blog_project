<template>
  <div>
    <div class="background">
      <div class="box_big pattern1">
        <img src="../static/img/荷叶.jpg" alt="">
        <div class="image1">
<!--          9.8 午  轮播图-->
          <ul :style="{left:move+'px'}">
            <li><img src="../static/img/春.jpg" alt=""></li>
            <li><img src="../static/img/夏.jpg" alt=""></li>
            <li><img src="../static/img/秋.jpg" alt=""></li>
            <li><img src="../static/img/冬.jpg" alt=""></li>
            <li><img src="../static/img/春.jpg" alt=""></li>
          </ul>
        </div>
        <div class="font1">
          <div class="font2">
            <h2>{{font}}</h2>
          </div>
          <div class="font2 font2_pattern">
            <h2>{{font1}}</h2>
          </div>
        </div>

      </div>
      <div class="box_big pattern2">
        <img src="../static/img/sea.jpg" alt="" class="img1">
        <div class="head" :style="{top: high1 +'px'}">
          <img src="../static/icon/博客.png">
          博客登录
        </div>
        <div class="login" v-on:mouseenter="pullDown" v-on:mouseleave="rise">
          <input type="text" v-model:value="userAccount" placeholder="userAccount">
          <input type="password" v-model:value="userPassword" placeholder="userPassword">
          <button>登录</button>
          <span class="forget">忘记密码？</span>
          <span class="register">注册</span>

        </div>

      </div>

    </div>
  </div>
</template>

<script>
export default {
  name: "login",
  data: function (){
    return{
      move: 0,
      index: 0,
      index1: 0,
      poetry: '逝者如斯夫  不舍昼夜  ',
      font: '',
      font1: '',
      high1: -80,
      userAccount: '',
      userPassword: ''

    }
  },
  methods: {
    change(){
      this.index++;
      this.move = this.index * (-400)
      if (this.index === 4){
        this.move = 0
        this.index = 0
      }
    },
    showFont(){
      if (this.index1 < 7){
        this.font = this.poetry.substr(0,this.index1)
      }
      this.index1++
      // console.log(this.index1)
      if (this.index1 >= 7){
        this.font1 = this.poetry.substr(this.index1,13)
        // console.log(this.font1)
      }
      if (this.index1 === 13){
        this.index1 = 0
        // console.log(this.index1)
      }
    },
    pullDown(){
      let timer = setInterval(
          ()=>{
              this.high1++
            if (this.high1 >= 26){
              clearInterval(timer)
            }
          },1
      )
    },
    rise(){
      let timer = setInterval(() =>{
        this.high1--
        if (this.high1 <= -80){
          clearInterval(timer)
        }
      },1)

    }
  },
  mounted() {
    // 这里写一个一开始就执行的函数
    this.timer = setInterval(() => {
      this.change()
    }, 2000);
    this.timer2 = setInterval(() =>{
      // console.log(this.poetry[3])
      this.showFont()
    },500)
  }
}
</script>

<style scoped lang="css">
  .background {
    position: relative;
    left: 50%;
    margin-left: -720px;
    width: 1440px;
    height: 722px;

  }
  .box_big {
    float: left;
    width: 720px;
    height: 722px;
  }
  .pattern1 img{
    width: 100%;
    height: 100%;
    object-fit: cover;

  }
  .pattern2 .img1 {
    width: 100%;
    height: 100%;
    object-fit: cover;
    
  }
  .box_big .image1 {
    overflow: hidden;
    position: absolute;
    top: 98px;
    left: 80px;
    width: 400px;
    height: 500px;
  }
  .image1 ul {
    position: absolute;
    top: 0;
    left: 0;
    width: 800%;
    margin-top: 0;
    padding: 0;
  }
  .image1 ul li {
    list-style: none;
    float: left;

  }
  .image1 ul li img {
    width: 400px;
    height: 500px;
    object-fit: cover;
  }
  .box_big .font1 {
    position: absolute;
    top: 163px;
    left: 536px;
    width: 140px;
    height: 394px;
  }
  .font1 .font2 {
    float: left;
    width: 40px;
    height: 250px;
    font-size: 22px;
    font-family: KAITI;
  }
  .font2 h2 {
    color: white;
  }
  .font1 .font2_pattern {
    margin-top: 132px;

  }
  .box_big .login {
    position: absolute;
    top: 98px;
    left: 763px;
    width: 361px;
    height: 522px;
    text-align: center;
    border-radius: 30px;
    background-color: cornflowerblue;
  }
  .login .forget {
    position: absolute;
    top: 490px;
    left: 20px;
    cursor: pointer;
  }
  .login .register {
    position: absolute;
    top: 490px;
    left: 290px;
    cursor: pointer;
  }
  .login input {
    display: block;
    width: 300px;
    height: 40px;
    margin: 50px auto 10px;
    text-indent: 1em;
    border: none;
    border-bottom: 2px solid lightsteelblue;

  }
  .login button {
    display: inline-block;
    width: 100px;
    height: 50px;
    margin: 20px ;
    border-radius: 25px;
    font-weight: bold;
    color: white;
    background-image: linear-gradient(to right,
    #a9bef4,#fb918e);
    border: none;
    cursor: pointer;
  }
  .box_big .head {
    position: absolute;
    top: -80px;
    /*原本top  26px*/
    left: 838px;
    width: 213px;
    height: 60px;
    border: 2px solid pink;
    border-radius: 30px;
    text-align: center;
    font-weight: bolder;
    font-family: AcadEref;
  }
  .head img {
    vertical-align: middle;
  }

</style>