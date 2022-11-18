<!--This layout file will show all of the components that surround our app. So for instance the header, draw on the side, and pages with images.
The route view component will load the /pages folder.-->
<!--To customize your layout, go to https://quasar.dev/layout-builder-->
<template>
  <q-layout view="lHr lpR fFf">

  <!--This is the header of our page.-->

    <q-header bordered class="bg-white text-black"> <!--This currently has a class of background white with black text - https://quasar.dev/style/theme-builder.-->
      <q-toolbar>
        <!--This is the 3 bar button to the left of your title-->
        <q-btn dense flat round icon="menu" @click="toggleLeftDrawer" />
        <!--Change the title of your page-->
        <q-toolbar-title class="text-weight-bold"> <!--We made the text bold. https://quasar.dev/style/typography-->
          Watchdog Financial Insider
        </q-toolbar-title>
      </q-toolbar>
    </q-header>

    <q-drawer show-if-above v-model="leftDrawerOpen" side="left" bordered>
      <!-- drawer content -->
    </q-drawer>

    <q-drawer show-if-above v-model="rightDrawerOpen" side="right" bordered>
      <!-- drawer content -->
    </q-drawer>

    <q-page-container>
      <router-view />
    </q-page-container>

  </q-layout>
</template>

<script>
import { ref } from 'vue'

export default {
  setup () {
    const leftDrawerOpen = ref(false)
    const rightDrawerOpen = ref(false)

    return {
      leftDrawerOpen,
      toggleLeftDrawer () {
        leftDrawerOpen.value = !leftDrawerOpen.value
      },

      rightDrawerOpen,
      toggleRightDrawer () {
        rightDrawerOpen.value = !rightDrawerOpen.value
      }
    }
  }
}
</script>
