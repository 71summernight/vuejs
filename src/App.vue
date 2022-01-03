<template>
  <div class="black-bg" v-if="isOpen===true">
      <div class="white-bg">
        <h4>상세페이지임</h4>
        <h4>상세페이지 내용임</h4>
      </div>
  </div>


  <div class="menu">
    <a  v-for="a in menu" :key="a">{{a}}</a>  
  </div>

  <div>
      <img class="room-img" src="https://i1.wp.com/www.gangnamoneroom.com/wp-content/uploads/2019/08/cdpc.jpg?resize=480%2C360" />
      <h4 @click="isOpen=true">{{products[0]}}</h4>
      <p>50만원</p>
      <button @click="count[0]++">허위매물신고</button>
      <span>신고수: {{count[0]}}</span>

  </div>

    <div>
      <img class="room-img" src="https://t1.daumcdn.net/liveboard/himartlifestyle/c6eeff73256a40f3babee8b04be70ec7.JPG" />
      <h4>{{products[1]}}</h4>
      <p>50만원</p>
      <button @click="count[1]++">허위매물신고</button>
      <span>신고수: {{count[1]}}</span>
  </div>

    <div>
        <img class="room-img" src="https://t1.daumcdn.net/liveboard/himartlifestyle/c6eeff73256a40f3babee8b04be70ec7.JPG" />
        <h4>{{products[2]}}</h4>
        <p>50만원</p>
        <button @click="count[2]++">허위매물신고</button>
        <span>신고수 :{{count[2]}}</span>
  </div>
</template>

<script>

export default {
  name: 'App',
  data(){
    return{
      isOpen:false,
      count:[0,0,0],
      menu:["HOME","SHOP","ABOUT"],
      products:["역삼동원룸","천호동원룸","마포구원룸"],

    }
  },
  methods:{
    increase(){

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
body{
  margin:0
}

div{
  box-sizing: border-box;
}

.black-bg{
  width:100%;
  height:100%;
  background-color: rgba(0,0,0,0.5);
  position: fixed;
  padding:20px;
}

.white-bg{
  width:100%;
  background-color: white;
  border-radius:8px;
  padding:20px;
}

.room-img{
  width:150px;
  margin-top:40px;
}
.menu{
  background-color: darkslateblue;
  padding :15px;
  border-radius: 5px;
}

.menu a{
  color:white;
  padding :10px;
}
</style>
