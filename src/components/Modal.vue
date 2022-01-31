<template>
    <div class="black-bg" v-if="isOpen===true">
      <div class="white-bg">  
          <img :src="oneRooms[clickRoomsNumber].image" />
          <h4>{{oneRooms[clickRoomsNumber].title}}</h4>
          <p>{{oneRooms[clickRoomsNumber].content}}</p>
          <!-- <input @input="month=$event.target.value"> -->
          <input v-model="month" >
          <p> {{month}}개월 선택함: {{oneRooms[clickRoomsNumber].price * month}}</p>
          <button @click="$emit('close')">닫기</button>
      </div>
  </div>
</template>

<script>
export default {
    name:"Modal",
    data(){
        return{
            month:3,
        }
    },
    watch:{
        month(a){
            if(isNaN(a)===true){
                alert("글자 입력하지 마셈");
                this.month=1;
            }
        },
    },

    updated(){
        if(this.month<=2){
            alert("3개월부터 받습니다.")
            this.month=3
        }
    },

    props:{
        oneRooms:Array,
        clickRoomsNumber:Number,
        isOpen:Boolean,
    }
}
</script>

<style>

</style>