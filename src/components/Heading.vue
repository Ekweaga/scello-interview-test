<script>



export default {
      data(){
         
   return {
    currentindex : 0,
    isvisible : this.$store.state.display,
    users : [],
    total:0,
    payableAmount:[]

   

  }
},

mounted(){
  this.users = this.$store.state.Users;
  let pp = this.users.map((item)=>{
    if(item.paidStatus == "Unpaid" || item.paidStatus == "Overdue"){
      this.payableAmount.push(item)
    }
  })
   this.total = this.payableAmount.reduce((accumulatedQuantity,user)=>accumulatedQuantity + user.amount,0)

}
  ,

 methods:{
    
    all(){
      this.$store.commit('all')
    },

      unpaid(){
    this.$store.commit('unPaid')
     
    },
    paid(){
      this.$store.commit('paid')
    },
    overdue(){
      this.$store.commit('overdue')
    }
   
  },
}

</script>


<template>
  <div class="md:w-[900px] ml-[0px] border-zinc-300 border-b-[1px] h-[45px] mb-[20px] overflowX-hidden ">
    <div class="flex justify-between items-center">
      <nav class="navbar navbar-expand-lg">
  <div class="container-fluid">
  
    
    <div class="" id="navbarNavAltMarkup">
      <div class="navbar-nav">
        <li class="nav-link active cursor-pointer" aria-current="page"  @click="all" >All</li>
        <li class="nav-link cursor-pointer"   @click="paid">Paid</li>
        <li class="nav-link cursor-pointer"  @click="unpaid">Unpaid</li>
        <li class="nav-link cursor-pointer"  @click="overdue">Overdue</li>
      </div>
    </div>
  </div>
</nav>
     

        <div>
          <span class="text-[#8F8AAC]">Total payable amount</span> : <span class="font-bold text-[#6D5BD0]">{{total}} USD</span>
        </div>

    </div>
    
    
  </div>
</template>


<style>
</style>
