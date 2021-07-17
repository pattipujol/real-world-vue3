<template>
  <div class="events">
    <img alt="Vue logo" src="../assets/logo.png" />
    <eventCard  v-for="event in events" :key="event.id" :event="event"/>
  </div>
</template>

<script>
// @ is an alias to /src
import eventCard from '@/components/eventCard.vue'

export default {
  name: 'EventList',
  components: {
    eventCard
  },
  data(){
    return{
      events: [
        {
         id: 5928101,
          category: 'animal welfare',
          title: 'Pinky Day',
          description: 'Find your new feline friend at this event.',
          location: 'Meow Town',
          date: 'January 28, 2022',
          time: '12:00',
          petsAllowed: true,
          organizer: 'Kat Laydee'
      },
      {
         id: 5928102,
          category: 'animal welfare',
          title: 'Rainbow Week',
          description: 'Find your new feline friend at this event.',
          location: 'Meow Town',
          date: 'January 28, 2022',
          time: '12:00',
          petsAllowed: true,
          organizer: 'Kat Laydee'
      },
      {
         id: 5928103,
          category: 'animal welfare',
          title: 'Fluffy ',
          description: 'Find your new feline friend at this event.',
          location: 'Meow Town',
          date: 'January 28, 2022',
          time: '12:00',
          petsAllowed: true,
          organizer: 'Kat Laydee'
      }
      ]
    }
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
