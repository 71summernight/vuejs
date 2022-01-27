
<template>
<!-- <div  class="start" :class="{end : isOpen}">  -->
  <!-- :calss="{밑에서 끝점 애니매이션 : 오른쪽은 true일때 실행 isOpen이 true}-->
<transition name="fade">
  <Modal  @close="isOpen=false" :oneRooms="oneRooms" :isOpen="isOpen" :clickRoomsNumber="clickRoomsNumber" />
  <!-- </div> -->
</transition>
  <div class="menu">
    <a  v-for="a in menu" :key="a">{{a}}</a>  
  </div>
  <Card v-for="(a,i) in oneRooms" :key="i" :oneRooms="oneRooms[i]" @openModal="isOpen=true" clickRoomsNumber="i" />
  <Discount></Discount>

  <button @click="priceSort" >가격순 정렬</button>
</template>

<script>
import data from './assets/data.js';
import Discount from "././components/Discount.vue";
import Modal from "././components/Modal.vue";
import Card from "././components/Card.vue"

export default {
  name: 'App',
  data(){
    //변수자리
    return{
      clickRoomsNumber:0,
      oneRooms:data,
      isOpen:false,
      count:[0,0,0],
      menu:["HOME","SHOP","ABOUT"],
      products:["역삼동원룸","천호동원룸","마포구원룸"],
    }
  },
  methods:{
    //함수자리
    priceSort(){
      this.oneRooms.sort(function(a,b){
        return a.price-b.price;
      })
    }
  },

  components: {
    //컴포넌트 임폴트
    Discount : Discount,
    Modal:Modal,
    Card:Card,
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

.discount{
  background-color: "#eeee";
  padding:10px;
  margin:10px;
  border-radius:5px;
}

/* .start{
  opacity:0;
  transition: all 1s;
}
.end{
  opacity:1;
} */

.fade-enter-from{
  opacity: 0;
}

.fade-enter-active{
  transition: all 1s;
}

.fade-enter-to{
  opacity:1;
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
