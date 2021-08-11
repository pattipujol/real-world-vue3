<template>
  <div class="event" :class="{'event-placeholder': !event}">
    <div v-if="event">
      <h1>{{ event.title }} [{{category}}]</h1>
      <p>{{ event.location }}</p>
      <p>{{ eventDateTime }}</p>
      <p>{{ event.description }}</p>
    </div>
    <div v-else>
      <p>Loading...</p>
    </div>
  </div>
</template>

<script>
import enventsServices from '@/services/EventsService.js'

export default {
    props: {
        id: {
            type: Number,
            required: true
        },
        category: {
            type: String
        }
    },
  data(){
    return {
      event: null,
    }
  },
computed: {
    eventDateTime() {
      return this.event.date + ' ' + this.event.time;
    }
  },  
  created(){
    enventsServices.getEvent(this.id).then(response => {
      console.log(response.data)
      this.event = response.data
    })
    .catch(error => {
      console.log(error)
    })
  },
}
</script>

<style scoped>

    .event{
        transition: all 0.4s ease-in;
        background-color: white;
        color: black;
        width: 100%;
        height: auto;
        margin: 0 auto;
    }
    .event.event-placeholder {
        background-color: greenyellow;
        color: indigo;
        font-size: 20px;
        font-weight: bold;
        display: inline-block;
        width: 400px;
        height: 200px;
        line-height: 180px;
    }

</style>