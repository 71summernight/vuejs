<template>
    <div :clickRoomsNumber="clickRoomsNumber">
      <img class="room-img" :src="oneRooms.image" />    
      <h4 @click="$emit('openModal',oneRooms.id)">{{oneRooms.title}}</h4>
      <p>{{oneRooms.price}}원</p>
   </div>
</template>

<script>
export default {
    name:"Card",
    props: { 
        oneRooms:Object,

    }
}
</script>

<style>

</style>