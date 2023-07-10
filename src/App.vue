<script >


export default {
      data(){
         
   return {
    currentindex : 0,
    all : this.$store.state.all,
    paid:this.$store.state.paid,
    unpaid:this.$store.state.unpaid,
    overdue:this.$store.state.overdue,
    self:this

   

  }

  
},

mounted(){
    console.log(self.$store.state.unpaid)
  }

}


</script>

<script setup>
import { RouterLink, RouterView } from 'vue-router'
import HelloWorld from './components/HelloWorld.vue'
import Heading from "./components/Heading.vue"
import MainContent from "./components/MainContent.vue"
import Paid from "./components/Paid.vue"
import Overdue from "./components/Overdue.vue"
import Unpaid from "./components/Unpaid.vue"
</script>

<template>
<div class="flex flex-col items-center justify-center  mt-[50px] ml-[120px] py-2">

<Heading/>
<div v-if="self.$store.state.paid">
<Paid/>
</div>
<div v-if="self.$store.state.all">
    <MainContent/>
</div>
 <div v-if="self.$store.state.unpaid">
    <Unpaid/>
 </div>
<div v-if="self.$store.state.overdue">
  <Overdue/>
</div>


</div>

  
</template>




