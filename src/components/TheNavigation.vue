<template>
  <div id="nav">

    <app-link id="logo" to="/">My Journal</app-link>

    <app-link 
        v-for="destination in destinations" 
        :key="destination.id" 
        :to="{ name: 'destination.show', params: { id: destination.id, slug: destination.slug } }"
      >
        {{ destination.name }}

      </app-link>

      <app-link :to="{name: 'protected'}">Dashboard</app-link>

      <app-link to="https://google.com">Google</app-link>

  </div>
</template>

<script>
import sourceData from '@/data.json'

export default {
  data() {
    return {
      destinations: sourceData.destinations
    }
  }
}
</script>

<style lang="css">
    #nav .my-active-link{
        color: red;
        border-bottom: 2px solid red;
    }
    #nav .my-active-link:first-child{
        color: white;
        border-bottom: 0;
    }
</style>