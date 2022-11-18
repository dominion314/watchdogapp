<!--This is our app.vue componenet which will load the layout of our app in the router-view. This connected to the /layouts folder.-->
<template>
  <router-view />
</template>

<script>
import { defineComponent } from 'vue'

export default defineComponent({
  name: 'App'
})
</script>
