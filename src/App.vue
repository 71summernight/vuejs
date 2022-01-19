<template>
  <div class="menu">
  <a v-for="i in menu" :key="i">{{i}}</a>

  </div>
  <div>
    <h4 class="red" >{{products[0]}}</h4>
    <p>50만원</p>
    <button @click="count[0]++">허위매물 신고버튼</button><span>신고수: {{count[0]}}</span>
    <img class="room-img" src="https://previews.123rf.com/images/paylessimages/paylessimages1412/paylessimages141271097/46223225-%EC%9B%90%EB%A3%B8.jpg" />
    </div> 
   <div>
      <h4 class="red" >{{products[1]}}</h4>
      <p>60만원</p>
      <button @click="count[1]++">허위매물 신고버튼</button><span>신고수: {{count[1]}}</span>
      <img class="room-img" src="https://tumblbug-pci.imgix.net/6e55fd0b261d97a413184662ebc64defcfea5279/92190de3b9504d76396dc8172f3a14d1e48dd3eb/ae361cecb08274a4bb0158fa000e29d7ed840841/452abddc-a03a-4c2a-b094-4ae8f33dc4d7.png?ixlib=rb-1.1.0&w=1240&h=930&auto=format%2Ccompress&lossless=true&fit=crop&s=ee05ae6acd3c5b8c5b43206749d819dc" />
  </div> 

   <div>
      <h4 class="red" >{{products[2]}}</h4>
      <p>70만원</p>
      <button @click="count[2]++">허위매물 신고버튼</button><span>신고수: {{count[2]}}</span>  
      <img class="room-img" src="https://pbs.twimg.com/media/DZy4az6UQAAX1f6.jpg" />
  </div> 

</template>

<script>


export default {
  name: 'App',
  data(){
    return{
      price1:80,
      price2:70,
      count:[0,0,0],
      menu:["Home","Shop","About"],
      products:["역삼동원룸","천호동원룸","마포구원룸"]
    }
  },
  methods:{
    
  },
  components: {
  }
}
</script>

<style>
.menu{
  background-color: darkslateblue;
  padding:15px;
  border-radius: 5px;
}
.menu a{
  color:white;
  padding :10px;

}

.room-img{
  width:150px;
}

#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
}
</style>
