<template>
    <div class="black-bg" v-if="isOpen===true">
      <div class="white-bg">  
          <h4>{{oneRooms[clickRoomsNumber].title}}</h4>
          <p>{{oneRooms[clickRoomsNumber].price}}</p>
          <p>{{oneRooms[clickRoomsNumber].content}}</p>
          <button @click="isOpen=false">닫기</button>
      </div>
  </div>
</template>

<script>
export default {
    name:"Modal",
}
</script>

<style>

</style>