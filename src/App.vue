<template>
  <img alt="Vue logo" src="./assets/logo.png">
  <div class="menu">
    <a v-for="(a,i) in menus" :key="i">{{ a }}</a>
  </div>
  <div v-for="(a,i) in productList" :key="i">
    <h4>{{a.name}}</h4>
    <p>{{ a.price }} 만원</p>
    <button v-on:click="increaseReport(i)">허위매물신고</button> <span>신고수 : {{ a.report }}</span>
  </div>
</template>
<script>



export default {
  name: 'App',
  data(){
    return{
      price1: 70,
      price2: 80,
      style1: 'color : blue',
      productList:[
        {
          name :'역삼동 원룸',
          price : '80',
          report: 0
        },
        {
          name :'청덕동 원룸',
          price : '50',
          report: 0
        },
        {
          name :'천호동 원룸',
          price : '70',
          report: 0
        }
      ],
      menus : ['Home','Shop','About']
    }
  },
  methods:{
    increaseReport(i){
      this.productList[i].report++;
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
  margin-top: 60px;
}
</style>
