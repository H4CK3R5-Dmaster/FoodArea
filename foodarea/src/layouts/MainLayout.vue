<template>
  <q-layout view="lHh Lpr lFf">
    <q-header >
      <q-toolbar>
        <q-btn
          flat
          dense
          round
          icon="menu"
          aria-label="Menu"
          @click="toggleLeftDrawer"
        />

        
      </q-toolbar>
      <div class="q-pa-sm">
        <div class="text-h3 txt">Food Area</div>
      </div>
      <q-img 
        src="../statics/food2.jpg" 
        class="header-image absolute-top"
      />
    </q-header>
        
    <q-drawer
      v-model="leftDrawerOpen"
      show-if-above
      bordered
    >
      <q-list>
        <q-item-label
          header
        >
          autre
        </q-item-label>

        <EssentialLink
          v-for="link in essentialLinks"
          :key="link.title"
          v-bind="link"
        />
      </q-list>
    </q-drawer>

    <q-page-container>
      <router-view />
    </q-page-container>
  </q-layout>
</template>

<script>
import EssentialLink from 'components/EssentialLink.vue'

const linksList = [
  {
    title: 'à propos',
    caption: 'version: 1.0.0',
    
  }
  
];

import { defineComponent, ref } from 'vue'

export default defineComponent({
  name: 'MainLayout',

  components: {
    EssentialLink
  },

  setup () {
    const leftDrawerOpen = ref(false)

    return {
      essentialLinks: linksList,
      leftDrawerOpen,
      toggleLeftDrawer () {
        leftDrawerOpen.value = !leftDrawerOpen.value
      }
    }
  }
})
</script>

<style lang="scss">
@import url('https://fonts.googleapis.com/css2?family=Libre+Baskerville:ital@1&display=swap');
  .header-image {
    height: 115px;
    width: 100%;
    z-index: -1;
    //margin-top: -30%;
    opacity: 0.80;
  
  }
  .txt {
    margin-left: 41%;
    font-family: Libre Baskerville;
    
    //color: gray;
  }

</style>
