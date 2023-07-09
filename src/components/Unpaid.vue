<script>



export default {
      data(){
         
   return {
    currentindex : 0,
    isvisible : this.$store.state.display,
    users : [],
    inputValue:"",
    viewImage:true,

   

  }
},

mounted(){
   this.users = this.$store.state.Users.filter((item)=>item.paidStatus == "Unpaid")
}
  ,

 methods:{
   Alrt(){
this.viewImage = !this.viewImage
},
    
     search(value){
    console.log(value)
    if(value == ""){
     this.users = this.$store.state.Users.filter((item)=>item.paidStatus == "Unpaid")
    }
    else{
      let filterValue = this.users.filter((item)=>
       item.firstName.toLowerCase().includes(value.toLowerCase()) || item.lastName.toLowerCase().includes(value.toLowerCase()) || item.email.toLowerCase().includes(value.toLowerCase())
      )

      this.users = filterValue;
    }

   }
  },
}

</script>


<template>
<div class="MainContent w-[900px] rounded-2xl border">
    <div class="filterSearch bg-white w-full ml-[0px] rounded-md flex justify-between p-2">
        <div class="flex gap-2">
          
               <select class="form-select shadow-md" aria-label="Default select example">
  <option selected>Filter</option>
  <option value="1">First Name</option>
  <option value="2">Last Name</option>
  <option value="3">Email</option>
</select>
<div class="bg-[#F4F2FF] p-2 flex items-center gap-2 rounded-md shadow-md">
  <img src="../assets/Shape/Search.png" class="w-[15px] h-[15px]"/>
    <input type="text" class="bg-transparent focus:outline-none focus:border-none w-[300px]  rounded-md placeholder-[#A9A4C2]" placeholder="Search Users by Name,Email,Date" v-model="inputValue"  @keyup="search(inputValue)"/>
</div>
                
            
        </div>

        <button class="bg-[#6D5BD0] text-white p-2 rounded-md">PAY DUES</button>

    </div>


    <div class="bg-white flex flex-col  ">

      <table  class="table">
       
         <thead class="bg-[#F4F2FF] p-2 table-light">
    <tr class="bg-[#F4F2FF]">
      <th> <input type="checkbox"/></th>
      <th scope="col">NAME</th>
      <th scope="col">USER STATUS</th>
      <th scope="col">PAYMENT STATUS</th>
       <th scope="col">AMOUNT</th>
        <th scope="col"></th>
      <th scope="col"> <img src="../assets/view/More.png" class="w-[13px]"/></th>

     
      
    </tr>
  </thead>
        <tbody>
          <tr v-for="user in users" :key="user.email" @click="Alrt">
            <td class="">
              <div class="flex mt-[20px] gap-4">
                 <input type="checkbox"/>
                   <img src="../assets/Icon/Master.png" class="w-[16px]" v-if="viewImage"/>
                     <img src="../assets/Icon/viewdown.png" class="w-[16px]" v-if="!viewImage"/></div>
                 

            </td>
            <td class="">
              <div class="flex flex-col ">
                  <h4 class="font-bold text-sm">
                {{user.firstName}} {{user.lastName}}
              </h4>
              <span class="text-[#ADAAC2]">{{user.email}}</span>
              </div>
            
              </td>

              <td class="flex flex-col gap-[2px]">
                <span v-bind:class="{
                  'bg-[#E6E6F2]  px-[4px] rounded-full text-[#6767FD] w-[80px] font-bold h-[23px] flex ': user.online == 'Active',
                  'bg-[#F2F0F9]  px-[4px] rounded-full text-[#B0ACC6] w-[80px] font-bold h-[23px] flex': user.online == 'Inactive'


                }"> <b class="text-[14px] font-extrabold px-[2px]">.</b><span class="font-bold">{{user.online}}</span></span>
                <span class="text-sm">Last login : {{user.lastLogin}}</span>
               
              </td>

              <td class="">
                  <span v-bind:class="{
                  'bg-[#CDFFCD]  px-[4px] rounded-full text-[#0D870D] w-[80px]  font-bold h-[23px] flex  ': user.paidStatus == 'Paid',
                  'bg-[#FFECCC]  px-[4px] rounded-full text-[#965E00] w-[80px]  font-bold h-[23px] flex ': user.paidStatus == 'Unpaid',
                    'bg-[#FFE0E0]  px-[4px] rounded-full text-[#D81C1C] w-[80px]  font-bold h-[23px] flex ': user.paidStatus == 'Overdue'



                }">
               <b class="text-[14px] font-extrabold px-[2px]">.</b><span class="font-bold">{{user.paidStatus}}</span></span>

                 <span class="text-sm">{{user.paidOn ? 'Paid on':null}} {{user.Dued ? 'Dued on':null}} {{user.Dues ? 'Dues on':null}} {{user.paidOn}} {{user.Dued}} {{user.Dues}}</span>
              </td>
              <td>
              <span class="font-bold"> ${{user.amount}}</span><br/><span>USD</span>
              </td>
             
              <td>
                <span class="cursor-pointer">
                 View more</span>
              </td>
              <td>
                <img src="../assets/view/More.png" class="w-[13px]"/>
              </td>
          </tr>
          </tbody>

        


      </table>
      
       


        

      

    </div>


</div>

</template>