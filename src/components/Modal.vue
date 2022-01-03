<template>
    <div class="black-bg" v-if="isOpen===true">
      <div class="white-bg">  
          <img :src="oneRooms[clickRoomsNumber].image" />
          <h4>{{oneRooms[clickRoomsNumber].title}}</h4>
          <p>{{oneRooms[clickRoomsNumber].price}}</p>
          <p>{{oneRooms[clickRoomsNumber].content}}</p>
          <button @click="$emit('close')">닫기</button>
      </div>
  </div>
</template>

<script>
export default {
    name:"Modal",
   
    props:{
        oneRooms:Array,
        clickRoomsNumber:Number,
        isOpen:Boolean,
    }
}
</script>

<style>

</style>