<script>



export default {
      data(){
         
   return {
    currentindex : 0,
    isvisible : this.$store.state.display,
    users : [],
    inputValue:"",
    empty:"",
    userActivity:[],
    unpaid:this.$store.state.unpaid,
    count:this.$store.state.count,
    page:1,
    displayDetails:false,

   

  }
},

created(){
   this.users = this.$store.state.Users.slice( (this.page - 1) * 5, (this.page - 1) * 5 + 5  )
   this.userActivity = this.$store.state.Users.map((item)=>{
    return item.activity
   })
   console.log(this.userActivity)
   console.log(this.users)
}
  ,

 methods:{

  showDetails(id){
    this.users.forEach((item)=>{
      if(item.id === id){
 this.displayDetails = !this.displayDetails
 console.log(id)
 return;
      }
      else{
        return;
      }
    })

   

  },

  setPage(pageNumber){
      this.page = pageNumber
      this.users = this.$store.state.Users.slice( (this.page - 1) * 5, (this.page - 1) * 5 + 5  )
      console.log(this.page)
  },
    
   search(value){
    console.log(value)
    if(value == ""){
       this.users = this.$store.state.Users.slice( (this.page - 1) * 5, (this.page - 1) * 5 + 5  )
    }
    else{
      let filterValue = this.$store.state.Users.filter((item)=>
       item.firstName.toLowerCase().includes(value.toLowerCase()) || item.lastName.toLowerCase().includes(value.toLowerCase()) || item.email.toLowerCase().includes(value.toLowerCase())
      )
      if(filterValue.length == 0){
        this.empty="NO RECORDS FOUND"
        return;
      }

      this.users = filterValue;
      this.empty=""
    }

   },
   paid(){
    let paidUsers=this.$store.state.Users.slice( (this.page - 1) * 5, (this.page - 1) * 5 + 5  ).map((item)=>{
      if(item.paidStatus == "Unpaid"){
      item.paidStatus = "Paid"
      }
    })
  this.users = paidUsers;
   }
  },
}

</script>

<script>


</script>


<template>

<div class="MainContent w-[900px] rounded-2xl border relative">
    <div class="filterSearch bg-white w-full ml-[0px] rounded-md flex justify-between p-2">
        <div class="flex gap-2">
          
               <select class="form-select" aria-label="Default select example">
  <option selected>Filter</option>
  <option value="1">First Name</option>
  <option value="2">Last Name</option>
  <option value="3">Email</option>
</select>
<div class="bg-[#F4F2FF] p-2">
    <input type="text" class="bg-transparent focus:outline-none focus:border-none w-[300px] px-3 rounded-md placeholder-[#A9A4C2]" placeholder="Search Users by Name,Email,Date" v-model="inputValue"  @keyup="search(inputValue)"/>
</div>
                
            
        </div>

        <button class="bg-[#6D5BD0] text-white p-2 rounded-md">PAY DUES</button>

    </div>


    <div class="flex flex-col">

      <div v-if="empty">
          {{empty}}
      </div>

      <table  class="table" v-if="users">
       
         <thead class="thead-dark">
    <tr class="">
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
          <tr v-for="user in users" :key="user?.email">
            <td class="">
              <div class="flex mt-[20px] gap-4">
                 <input type="checkbox" @click="paid"/>
                  <img src="../assets/Icon/Master.png" class="w-[13px]"/></div>
                 

            </td>
            <td class="">
              <div class="flex flex-col ">
                  <h4 class="font-bold text-sm">
                {{user.firstName}} {{user.lastName}}
              </h4>
              <span class="text-[#ADAAC2]">{{user.email}}</span>
              </div><br/>
              <table>
                 
         <thead class="thead-dark">
    <tr class="">
      
      <th scope="col" class="text-sm">DATE</th>
      <th scope="col" class="text-sm">ACTIVITY</th>
      <th scope="col" class="text-sm">DETAIL</th>
    </tr>
  </thead>
  <tbody>
    <tr v-for="userActivity in user.activity" :key="userActivity.details">
      <td class="text-sm">{{userActivity.Date}}</td>
      <td class="text-sm">{{userActivity.activity}}</td>
      <td class="text-sm">{{userActivity.details}}</td>
      </tr>
  </tbody>
              </table>
             
            
              </td>

              <td class="">
                <span v-bind:class="{
                  'bg-[#E6E6F2] px-[4px]  rounded-full text-[#6767FD] w-[80px] font-bold h-[23px] flex gap-[2px]': user.online == 'Active',
                  'bg-[#F2F0F9]  px-[4px] rounded-full text-[#B0ACC6] w-[80px] font-bold h-[23px] flex gap-[2px]': user.online == 'Inactive'


                }"> <span class="text-[13px] font-extrabold px-[2px] ">.</span><span class="font-bold">{{user.online}}</span></span>
                <span class="text-sm">Last login : {{user.lastLogin}}</span>
               
              </td>

              <td class="">
                  <span v-bind:class="{
                  'bg-[#CDFFCD]  px-[4px] rounded-full text-[#0D870D] w-[55px] font-bold h-[23px] flex gap-[2px] ': user.paidStatus == 'Paid',
                  'bg-[#FFECCC]  px-[4px] rounded-full text-[#965E00] w-[80px]  font-bold  h-[23px] flex gap-[2px] ': user.paidStatus == 'Unpaid',
                    'bg-[#FFE0E0]  px-[4px] rounded-full text-[#D81C1C] w-[80px]  font-bold  h-[23px] flex gap-[2px] ': user.paidStatus == 'Overdue'



                }">
               <b class="text-[13px] font-extrabold px-[2px] ">.</b> <span class="font-bold">{{user.paidStatus}}</span></span>

                 <span class="text-sm">{{user.paidOn ? 'Paid on':null}} {{user.Dued ? 'Dued on':null}} {{user.Dues ? 'Dues on':null}} {{user.paidOn}} {{user.Dued}} {{user.Dues}}</span>
              </td>
              <td>
              <span class="font-bold"> ${{user.amount}}</span><br/><span>USD</span>
              </td>
             
              <td>
                <span class="cursor-pointer text-sm" @click="showDetails(user.id)">
                 View more</span>
                 
              </td>
              <td>
                <img src="../assets/view/More.png" class="w-[13px] cursor-pointer"/>
              </td>
              
          </tr>
          
          
          </tbody>
      

        


      </table>
      
       


        

      

    </div>
<div class="absolute right-0 -bottom-[20px]">

 <nav aria-label="Page navigation example ">
  <ul class="pagination">
    <li class="page-item">
      <a class="page-link" href="#" aria-label="Previous">
        <span aria-hidden="true">&laquo;</span>
      </a>
    </li>
    <li class="page-item" @click="setPage(1)"><span class="page-link cursor-pointer">1</span></li>
    <li class="page-item" @click="setPage(2)"><span class="page-link cursor-pointer">2</span></li>
    <li class="page-item" @click="setPage(3)"><span class="page-link cursor-pointer">3</span></li>
    <li class="page-item">
      <span class="page-link" aria-label="Next">
        <span aria-hidden="true">&raquo;</span>
      </span>
    </li>
  </ul>
</nav></div>

</div>


</template>

<style >

</style>