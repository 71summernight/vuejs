
<template>
  <Modal  @close="isOpen=false" :oneRooms="oneRooms" :isOpen="isOpen" :clickRoomsNumber="clickRoomsNumber" />
  <div class="menu">
    <a  v-for="a in menu" :key="a">{{a}}</a>  
  </div>
  <Card v-for="(a,i) in oneRooms" :key="i" :oneRooms="oneRooms[i]" @openModal="isOpen=true; clickRoomsNumber=i" />
  <Discount></Discount>
</template>

<script>
import data from './assets/data.js';
import Discount from "././components/Discount.vue";
import Modal from "././components/Modal.vue";
import Card from "././components/Card.vue"

export default {
  name: 'App',
  data(){
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
  },

  components: {
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
