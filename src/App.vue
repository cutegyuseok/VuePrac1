<template>
<div class="black-bg" v-if="windowStatus">
  <div class="white-bg">
    <h4>상세 정보</h4>
    <h4>{{ products[windowProductIndex].title}}</h4>
    <p> {{ products[windowProductIndex].content }}  </p>
    <button v-on:click="increaseReport(windowProductIndex)">허위매물신고</button> <span>신고수 : {{ products[windowProductIndex].report }}</span>
    <br>
    <button @click="windowStatus =false" style="margin-top: 10px;">닫기</button>
  </div>
</div>



  <div class="menu">
    <a v-for="(a,i) in menus" :key="i">{{ a }}</a>
  </div>

  <div class="product" v-for="(a,i) in products" :key="i">
    <img :src="a.image" class="productMainImage">
    <h4 @click="windowStatus =true , windowProductIndex = i">{{a.title}}</h4>
    <p>{{ a.price }} 만원</p>
  </div>
</template>



<script>


export default {
  name: 'App',
  data(){
    return{
      windowStatus : false,
      windowProductIndex: 0,
      style1: 'color : blue',
      menus : ['Home','Shop','About'],
      products : [{
    id : 0,
    title: "Sinrim station 30 meters away",
    image: "https://codingapple1.github.io/vue/room0.jpg",
    content: "18년 신축공사한 남향 원룸 ☀️, 공기청정기 제공",
    price: 340000,
    report:0
    },
    {
    id : 1,
    title: "Changdong Aurora Bedroom(Queen-size)",
    image: "https://codingapple1.github.io/vue/room1.jpg",
    content: "침실만 따로 있는 공용 셰어하우스입니다. 최대 2인 가능",
    price: 450000,
    report:0
    },
    {
    id : 2,
    title: "Geumsan Apartment Flat",
    image: "https://codingapple1.github.io/vue/room2.jpg",
    content: "금산오거리 역세권 아파트입니다. 애완동물 불가능 ?",
    price: 780000,
    report:0
    },
    {
    id : 3,
    title: "Double styled beds Studio Apt",
    image: "https://codingapple1.github.io/vue/room3.jpg",
    content: "무암동인근 2인용 원룸입니다. 전세 전환가능",
    price: 550000,
    report:0
    },
    {
    id : 4,
    title: "MyeongIl Apartment flat",
    image: "https://codingapple1.github.io/vue/room4.jpg",
    content: "탄천동 아파트 월세, 남향, 역 5분거리, 허위매물아님",
    price: 680000,
    report:0
    },
    {
    id : 5,
    title: "Banziha One Room",
    image: "https://codingapple1.github.io/vue/room5.jpg",
    content: "반지하 원룸입니다. 비올 때 물가끔 새는거 빼면 좋아요",
    price: 370000,
    report:0
  }]
    }
  },
  methods:{
    increaseReport(i){
      this.products[i].report++;
    }
  },
  components: {
  }
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
}

.menu{
  background: darkslateblue;
  padding: 15px;
  border-radius: 5px;
}

.menu a {
  color: white;
  padding: 10px;
}

.product {
  margin-top: 10px;
}

.productMainImage{
  width: 70%;
  margin-top: 40px;
}

body{
  margin: 0;
}

div {
  box-sizing: border-box;
}

.black-bg { 
  width: 100%; height: 100%;
  background: rgba(0, 0, 0, 0.5);
  position: fixed; padding: 20px;
}

.white-bg {
  width: 100%; background: white;
  border-radius: 8px;
  padding: 20px;
}


</style>
