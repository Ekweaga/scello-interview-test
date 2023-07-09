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
    id:0,
    viewImage:true,
    sortValue:""

   

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

  sort(){
    console.log(this.sortValue)
    if(this.sortValue == "all"){
      this.users = this.$store.state.Users.slice( (this.page - 1) * 5, (this.page - 1) * 5 + 5  )
    }

    if(this.sortValue == "firstName"){
      let sortedNames= this.$store.state.Users.slice( (this.page - 1) * 5, (this.page - 1) * 5 + 5  ).sort((a,b)=>{
        if(a.firstName < b.firstName){
          return;
        }

         if(a.firstName > b.firstName){
          return;
        }


      })
      this.users = sortedNames
    }

  }
,
  showDetails(id){
    this.users.forEach((item)=>{
      if(item.id == id){
        this.displayDetails = !this.displayDetails
        this.viewImage = !this.viewImage
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
      let filterValue = this.users.filter((item)=>
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
       
          
               <select class="form-select shadow-md" aria-label="Default select example" v-model="sortValue" @change="sort">
  <option value="all"> <img src="../assets/Shape/Filter.png" class="w-[15px] h-[15px]"/>Filter</option>
  <option value="firstName">First Name</option>
  <option value="lastName">Last Name</option>
  <option value="email">Email</option>
</select>
<div class="bg-[#F4F2FF] p-2 flex gap-2 items-center rounded-md shadow-md">
  <img src="../assets/Shape/Search.png" class="w-[15px] h-[15px]"/>
    <input type="text" class="bg-transparent focus:outline-none focus:border-none w-[300px]  rounded-md placeholder-[#A9A4C2]" placeholder="Search Users by Name,Email,Date" v-model="inputValue"  @keyup="search(inputValue)"/>
</div>
                
            
        </div>

        <button class="bg-[#6D5BD0] text-white p-2 rounded-md">PAY DUES</button>

    </div>




     

      <table  class="table" >
     
       
         <thead class="table-light">

    <tr class="bg-[#F2F0F9]">
      <th > <input type="checkbox" class="w-[20px] text-[20px]"/></th>
      <th scope="col" class="text-[#7F79A0] text-sm">NAME</th>
      <th scope="col">USER STATUS</th>
      <th scope="col">PAYMENT STATUS</th>
       <th scope="col">AMOUNT</th>
        <th scope="col"></th>
      <th scope="col"> <img src="../assets/view/More.png" class="w-[13px]"/></th> 
    </tr>

  </thead>

        <tbody>
          <template v-for="user in users" :key="user?.id" >
            
          <tr class="cursor-pointer hover:bg-[#F2F0F9]" @click="showDetails(user.id)" data-toggle="collapse" data-target="">

            <td class="">
              <div class="flex mt-[20px] gap-4">
                 <input type="checkbox" @click="paid" class="w-[20px] text-[20px]"/>
                  <img src="../assets/Icon/Master.png" class="w-[16px]" v-if="viewImage"/>
                     <img src="../assets/Icon/viewdown.png" class="w-[16px]" v-if="!viewImage"/>
                  </div>
            </td>


            <td class="" >
            
                  <h4 class="font-bold text-sm">
                {{user.firstName}} {{user.lastName}}
              </h4>
              <span class="text-[#ADAAC2]">{{user.email}}</span>
            
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
                  'bg-[#CDFFCD]  px-[4px] rounded-full text-[#0D870D] w-[55px] font-bold h-[23px] flex gap-[2px]  ': user.paidStatus == 'Paid',
                  'bg-[#FFECCC]  px-[4px] rounded-full text-[#965E00] w-[80px]  font-bold  h-[23px] flex gap-[2px] ': user.paidStatus == 'Unpaid',
                    'bg-[#FFE0E0]  px-[4px] rounded-full text-[#D81C1C] w-[80px]  font-bold  h-[23px] flex gap-[2px]  ': user.paidStatus == 'Overdue'

                }">
               <b class="text-[13px] font-extrabold px-[2px] ">.</b> <span class="font-bold">{{user.paidStatus}}</span></span>

                 <span class="text-sm">{{user.paidOn ? 'Paid on':null}} {{user.Dued ? 'Dued on':null}} {{user.Dues ? 'Dues on':null}} {{user.paidOn}} {{user.Dued}} {{user.Dues}}</span>
              </td>

              <td>
              <span class="font-bold"> ${{user.amount}}</span><br/><span>USD</span>
              </td>
             
              <td>
                <span class="cursor-pointer text-sm " data-toggle="collapse" aria-expanded="false" aria-controls="collapseExample" href="#collapseExample" data-target="#collapseExample" @click="showDetails(user.id)" >
                 View more</span>
              </td>

              <td>
                <img src="../assets/view/More.png" class="w-[13px] cursor-pointer"/>
              </td> 
          </tr>
          

<tr>

          <table class=" table table-light  " v-if="user.id == id" >

                <thead >    
        	<tr class="text-sm ">
          <th class="text-sm" >NAME</th>
          <th class="text-sm" colspan="">ACTIVITY</th>
          <th class="text-sm" colspan="">DETAIL</th>
        </tr>
        </thead>

        <tbody>
          <template  v-for="userActivity in user.activity" :key="userActivity.details">
          <tr >
          <td class="text-sm">{{userActivity.Date}}</td>
           <td colspan="" class="text-sm">{{userActivity.activity}}</td>
            <td colspan="" class="text-sm">{{userActivity.details}}</td>

          </tr>
          </template>
        </tbody>
  
          
          
</table></tr>
          
         
          </template>
          </tbody>
      

        


      </table>
      
       


        

      

    
<div class="absolute right-0 -bottom-[20px] pagination">

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
tr.collapse.in {
  display:table-row;
}
tr:hover{
  background:#F2F0F9;
}

tr th td{
  font-size:15px;
}
.pagination{
  z-index:2px;
}


</style>