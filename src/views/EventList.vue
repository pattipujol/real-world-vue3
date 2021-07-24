<template>
  <div class="events">
    <img alt="Vue logo" src="../assets/logo.png" />
    <eventCard  v-for="event in events" :key="event.id" :event="event"/>
  </div>
</template>

<script>
// @ is an alias to /src
import eventCard from '@/components/eventCard.vue'
import enventsServices from '@/services/EventsService.js'

export default {
  name: 'EventList',
  components: {
    eventCard
  },
  data(){
    return{
      events: []
    }
  },
  created(){
    enventsServices.getEvents().then(response => {
      console.log(response.data)
      this.events = response.data
    })
    .catch(error => {
      console.log(error)
    })
  }
}
</script>

<style scoped>
.events {
  display: flex;
  flex-direction: column;
  align-items: center;
}
</style>
