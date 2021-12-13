<template>
  <q-page class="flex flex-center">
    <!-- <img
      alt="Quasar logo"
      src="~assets/quasar-logo-vertical.svg"
      style="width: 200px; height: 200px"
    > -->
     <q-btn-group push>
      <q-btn color="blue" push size="22px"  label="Connexion" />
      
      <q-btn color="red" push size="22px" label="Inscription" />
    </q-btn-group>
    
  </q-page>
</template>

<script>
import { defineComponent } from 'vue';





export default defineComponent({
  name: 'PageIndex',

  
})


</script>
<style lang="scss">
  .btn{
    margin-top: -15%;
  }
</style>