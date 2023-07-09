<script>
import { createApp } from 'vue'
import { createStore } from 'vuex'

export  const store = createStore({
  state () {
    return {
      Users:[

           {
            id:1,
                 firstName:"Elizabeth",
            lastName:"Joy",
            email:"lizzy@gmail.com",
            online:"Active",
            paidStatus:"Unpaid",
            lastLogin:"12/JAN/2008",
            paidOn:"14/MAR/2009",
            amount:200,
            show:false,
                activity:[
                    {
                    id:1
                  },
              {
                  Date:"12/JAN/2008",
                  activity:"Lorem ipsum.",
                  details:"Lorem ipsum dolor  suspendisse vestibulum."
              },
              {
 Date:"12/FEB/2008",
                  activity:"Lorem ipsum dolo.",
                  details:"Lorem Ultricies suspendisse vestibulum."
              },
              {
                 Date:"12/NOV/2008",
                  activity:"Lorem ipsum .",
                  details:"Lorem ipsum dol semper morbi id nunc, adipiscing vitae. Ultricies suspendisse vestibulum."
              }

            ]
            },
        {
            id:2,
            firstName:"Ekweaga",
            lastName:"Charles",
            email:"hikay133@gmail.com",
            online:"Active",
            paidStatus:"Paid",
            lastLogin:"12/JAN/2006",
            paidOn:"14/MAR/2007",
            amount:200,
            activity:[
              {
                  Date:"12/JAN/2004",
                  activity:"Lorem ipsum dolor .",
                  details:"Lorem ipsum suspendisse vestibulum."
              },
              {
 Date:"12/FEB/2004",
                  activity:"Lorem ipsum .",
                  details:"Lorem ipsumsuspendisse vestibulum."
              },
              {
                 Date:"Nov/12/2004",
                  activity:"Lorem ipsum  Ultricies.",
                  details:"Lorem iid nunc, adipiscing vestibulum."
              }

            ]

        },
         {
            id:3,
             firstName:"Samuel",
            lastName:"Komolafe",
            email:"samuel@gmail.com",
            online:"Active",
            paidStatus:"Paid",
            lastLogin:"12/JAN/2009",
            paidOn:"14/MAR/2009",
            amount:1200,
                activity:[
              {
                  Date:"12/JAN/2007",
                  activity:"Lorem ipsum .",
                  details:"Lorem Ultricies suspendisse vestibulum."
              },
              {
 Date:"12/FEB/2007",
                  activity:"Lorem ipsum ",
                  details:"Lorem ipsum dolor sit amet, vestibulum."
              },
              {
                 Date:"12/NOV/2007",
                  activity:"Lorem ipsum .",
                  details:"Lorem ipsum dolor sit amet, vestibulum."
              }

            ]
         },

          {
              id:4,
                 firstName:"William",
            lastName:"Charles",
            email:"willaim@gmail.com",
            online:"Active",
            paidStatus:"Overdue",
            lastLogin:"12/JAN/2006",
            Dued:"14/MAR/2007",
            amount:1000,
                activity:[
              {
                  Date:"12/JAN/2009",
                  activity:"Lorem ipsum dolor.",
                  details:"Lorem ipsum dolor sit amet, consectetidulum."
              },
              {
 Date:"12/FEB/2009",
                  activity:"Lorem ipsum dolor sit amet, consectetur adipiscing elit. Ultricies.",
                  details:"Lorem ipsum dolor sit amet, consectetur adipiscing elit. Rhoncus, sed purus eu semper morbi id nunc, adipiscing vitae. Ultricies suspendisse vestibulum."
              },
              {
                 Date:"12/NOV/2009",
                  activity:"Lorem ipsum .",
                  details:"Lorem ltricies suspendisse vestibulum."
              }

            ]
            },
          {
              id:5,
             firstName:"Adebayo",
            lastName:"Muhammed",
            email:"adebayo@gmail.com",
            online:"Active",
            paidStatus:"Paid",
            lastLogin:"12/FEB/2006",
            paidOn:"14/MAR/2007",
            amount:2500,
                activity:[
              {
                  Date:"12/JAN/2019",
                  activity:"Lorem ipsum dolor.",
                  details:"Lorem suspendisse vestibulum."
              },
              {
 Date:"12/FEB/2019",
                  activity:"Lorem ipsum.",
                  details:"Lorem ipsum dolor sit amet, Ultricies suspendisse vestibulum."
              },
              {
                 Date:"Nov/12/2019",
                  activity:"Lorem ipsum dolo",
                  details:"Lorem ipsum dolor sit amet, estibulum."
              }

            ]
          },

           {
              id:6,
            firstName:"Ekweaga",
            lastName:"Charles",
            email:"hikay@gmail.com",
            online:"Active",
            paidStatus:"Overdue",
            lastLogin:"12/JAN/2006",
            Dued:"14/MAR/2007",
            amount:650,
            activity:[
              {
                  Date:"12/JAN/2004",
                  activity:"Lorem ipsum dolor.",
                  details:"Loremltricies suspendisse vestibulum."
              },
              {
 Date:"12/FEB/2004",
                  activity:"Lorem ipsum.",
                  details:"Lorem ipsum dolorricies suspendisse vestibulum."
              },
              {
                 Date:"12/NOV/2004",
                  activity:"Lorem ipsum dolor sit amet, consectetur adipiscing elit. Ultricies.",
                  details:"Lorem. Ultricies suspendisse vestibulum."
              }

            ]

        },

          {
              id:7,
             firstName:"Oluwa",
            lastName:"Timi",
            email:"oluwa@gmail.com",
            online:"Inactive",
            paidStatus:"Unpaid",
            lastLogin:"12/JAN/2006",
            Dues:"14/MAR/2007",
            amount:4500,
                activity:[
         {
                  Date:"12/JAN/2016",
                  activity:"Lorem ipsum dolor sit amet, consectetur adipiscing elit. Ultricies.",
                  details:"Lorem ipsum dolor sit amet, consectetur adipiscing elit. Rhoncus, sed purus eu semper morbi id nunc, adipiscing vitae. Ultricies suspendisse vestibulum."
              },
              {
 Date:"12/FEB/2016",
                  activity:"Lorem ipsum dolor sit amet, consectetur adipiscing elit. Ultricies.",
                  details:"Lorem ipsum dolor sit amet, consectetur adipiscing elit. Rhoncus, sed purus eu semper morbi id nunc, adipiscing vitae. Ultricies suspendisse vestibulum."
              },
              {
                 Date:"12/NOV/2016",
                  activity:"Lorem ipsum dolor sit amet, consectetur adipiscing elit. Ultricies.",
                  details:"Lorem ipsum dolor sit amet, consectetur adipiscing elit. Rhoncus, sed purus eu semper morbi id nunc, adipiscing vitae. Ultricies suspendisse vestibulum."
              }

            ]
          },

           {
              id:8,
                 firstName:"William",
            lastName:"Charles",
            email:"willaim@gmail.com",
            online:"Active",
            paidStatus:"Overdue",
            lastLogin:"12/JAN/2006",
            paidOn:"14/MAR/2007",
            amount:1000,
                activity:[
              {
                  Date:"12/JAN/2009",
                  activity:"Lorem ipsum dolor sit amet, consectetur adipiscing elit. Ultricies.",
                  details:"Lorem ipsum dolor sit amet, consectetur adipiscing elit. Rhoncus, sed purus eu semper morbi id nunc, adipiscing vitae. Ultricies suspendisse vestibulum."
              },
              {
 Date:"12/FEB/2009",
                  activity:"Lorem ipsum dolor sit amet, consectetur adipiscing elit. Ultricies.",
                  details:"Lorem ipsum dolor sit amet, consectetur adipiscing elit. Rhoncus, sed purus eu semper morbi id nunc, adipiscing vitae. Ultricies suspendisse vestibulum."
              },
              {
                 Date:"12/NOV/2009",
                  activity:"Lorem ipsum dolor sit amet, consectetur adipiscing elit. Ultricies.",
                  details:"Lorem ipsum dolor sit amet, consectetur adipiscing elit. Rhoncus, sed purus eu semper morbi id nunc, adipiscing vitae. Ultricies suspendisse vestibulum."
              }

            ]
            },
          {
              id:9,
             firstName:"Ekweaga",
            lastName:"Victor",
            email:"vicking@gmail.com",
            online:"Inactive",
            paidStatus:"Unpaid",
            lastLogin:"12/JAN/2006",
            Dues:"14/MAR/2007",
            amount:2000,
                activity:[
               {
                  Date:"12/JAN/2013",
                  activity:"Lorem ipsum dolor sit amet, consectetur adipiscing elit. Ultricies.",
                  details:"Lorem ipsum dolor sit amet, consectetur adipiscing elit. Rhoncus, sed purus eu semper morbi id nunc, adipiscing vitae. Ultricies suspendisse vestibulum."
              },
              {
 Date:"12/FEB/2013",
                  activity:"Lorem ipsum dolor sit amet, consectetur adipiscing elit. Ultricies.",
                  details:"Lorem ipsum dolor sit amet, consectetur adipiscing elit. Rhoncus, sed purus eu semper morbi id nunc, adipiscing vitae. Ultricies suspendisse vestibulum."
              },
              {
                 Date:"22/NOV/2013",
                  activity:"Lorem ipsum dolor sit amet, consectetur adipiscing elit. Ultricies.",
                  details:"Lorem ipsum dolor sit amet, consectetur adipiscing elit. Rhoncus, sed purus eu semper morbi id nunc, adipiscing vitae. Ultricies suspendisse vestibulum."
              }

            ]
          },

          {
              id:10,
             firstName:"Oluwaseyi",
            lastName:"adebayo",
            email:"seyi@gmail.com",
            online:"Active",
            paidStatus:"Unpaid",
            lastLogin:"12/JAN/2006",
            Dues:"14/MAR/2007",
            amount:2400,
                activity:[
              {
                  Date:"12/JAN/2011",
                  activity:"Lorem ipsum dolor sit amet, consectetur adipiscing elit. Ultricies.",
                  details:"Lorem ipsum dolor sit amet, consectetur adipiscing elit. Rhoncus, sed purus eu semper morbi id nunc, adipiscing vitae. Ultricies suspendisse vestibulum."
              },
              {
 Date:"12/FEB/2011",
                  activity:"Lorem ipsum dolor sit amet, consectetur adipiscing elit. Ultricies.",
                  details:"Lorem ipsum dolor sit amet, consectetur adipiscing elit. Rhoncus, sed purus eu semper morbi id nunc, adipiscing vitae. Ultricies suspendisse vestibulum."
              },
              {
                 Date:"12/NOV/2011",
                  activity:"Lorem ipsum dolor sit amet, consectetur adipiscing elit. Ultricies.",
                  details:"Lorem ipsum dolor sit amet, consectetur adipiscing elit. Rhoncus, sed purus eu semper morbi id nunc, adipiscing vitae. Ultricies suspendisse vestibulum."
              }

            ]
          },

          {
              id:11,
             firstName:"Ayomide",
            lastName:"Ife",
            email:"ife@gmail.com",
            online:"Active",
            paidStatus:"Unpaid",
            lastLogin:"12/JAN/2012",
            Dues:"14/MAR/2012",
            amount:7500,
                activity:[
            {
                  Date:"12/APR/2010",
                  activity:"Lorem ipsum dolor sit amet, consectetur adipiscing elit. Ultricies.",
                  details:"Lorem ipsum dolor sit amet, consectetur adipiscing elit. Rhoncus, sed purus eu semper morbi id nunc, adipiscing vitae. Ultricies suspendisse vestibulum."
              },
              {
 Date:"12/FEB/2010",
                  activity:"Lorem ipsum dolor sit amet, consectetur adipiscing elit. Ultricies.",
                  details:"Lorem ipsum dolor sit amet, consectetur adipiscing elit. Rhoncus, sed purus eu semper morbi id nunc, adipiscing vitae. Ultricies suspendisse vestibulum."
              },
              {
                 Date:"12/APR/2010",
                  activity:"Lorem ipsum dolor sit amet, consectetur adipiscing elit. Ultricies.",
                  details:"Lorem ipsum dolor sit amet, consectetur adipiscing elit. Rhoncus, sed purus eu semper morbi id nunc, adipiscing vitae. Ultricies suspendisse vestibulum."
              }
            ]
          },

           {
              id:12,
            firstName:"Odufuwa",
            lastName:"Olamide",
            email:"ola@gmail.com",
            online:"Active",
            paidStatus:"Overdue",
            lastLogin:"12/AUG/2006",
            Dued:"14/MAR/2007",
            amount:900,
                activity:[
              {
                  Date:"12/SEP/2004",
                  activity:"Lorem ipsum dolor sit amet, consectetur adipiscing elit. Ultricies.",
                  details:"Lorem ipsum dolor sit amet, consectetur adipiscing elit. Rhoncus, sed purus eu semper morbi id nunc, adipiscing vitae. Ultricies suspendisse vestibulum."
              },
              {
 Date:"23/JUN/2004",
                  activity:"Lorem ipsum dolor sit amet, consectetur adipiscing elit. Ultricies.",
                  details:"Lorem ipsum dolor sit amet, consectetur adipiscing elit. Rhoncus, sed purus eu semper morbi id nunc, adipiscing vitae. Ultricies suspendisse vestibulum."
              },
              {
                 Date:"22/OCT/2004",
                  activity:"Lorem ipsum dolor sit amet, consectetur adipiscing elit. Ultricies.",
                  details:"Lorem ipsum dolor sit amet, consectetur adipiscing elit. Rhoncus, sed purus eu semper morbi id nunc, adipiscing vitae. Ultricies suspendisse vestibulum."
              }

            ]
            
            },

            {   id:13,
                 firstName:"William",
            lastName:"Charles",
            email:"willai32m@gmail.com",
            online:"Active",
            paidStatus:"Overdue",
            lastLogin:"31/JAN/2006",
            paidOn:"15/MAR/2007",
            amount:1000,
                activity:[
                
              {
                  Date:"30/JAN/2009",
                  activity:"Lorem ipsum dolor sit amet, consectetur adipiscing elit. Ultricies.",
                  details:"Lorem ipsum dolor sit amet, consectetur adipiscing elit. Rhoncus, sed purus eu semper morbi id nunc, adipiscing vitae. Ultricies suspendisse vestibulum."
              },
              {
 Date:"12/FEB/2009",
                  activity:"Lorem ipsum dolor sit amet, consectetur adipiscing elit. Ultricies.",
                  details:"Lorem ipsum dolor sit amet, consectetur adipiscing elit. Rhoncus, sed purus eu semper morbi id nunc, adipiscing vitae. Ultricies suspendisse vestibulum."
              },
              {
                 Date:"12/NOV/2009",
                  activity:"Lorem ipsum dolor sit amet, consectetur adipiscing elit. Ultricies.",
                  details:"Lorem ipsum dolor sit amet, consectetur adipiscing elit. Rhoncus, sed purus eu semper morbi id nunc, adipiscing vitae. Ultricies suspendisse vestibulum."
              }

            ]
            },

             {
                 id:14,
            firstName:"Ekweaga",
            lastName:"Charles",
            email:"hikay222@gmail.com",
            online:"Active",
            paidStatus:"Paid",
            lastLogin:"31/JAN/2006",
            paidOn:"18/JUL/2010",
            amount:200,
            activity:[
              {
                  Date:"4/FEB/2004",
                  activity:"Lorem ipsum dolor sit amet.",
                  details:"Lorem ipsum Ultricies suspendisse vestibulum."
              },
              {
 Date:"30/MAY/2004",
                  activity:"Lorem ipsum",
                  details:"Lorem ipsum cies suspendisse vestibulum."
              },
              {
                 Date:"12/DEC/2004",
                  activity:"Lorem ipsum dolo",
                  details:"Lorem ipsum dolor ltricies suspendisse vestibulum."
              }

            ]

        },

         
             {
                 id:15,
            firstName:"Victor",
            lastName:"Ayomide",
            email:"ekweaga@gmail.com",
            online:"Active",
            paidStatus:"Paid",
            lastLogin:"12/MAY/2006",
            paidOn:"13/JUL/2007",
            amount:200,
            activity:[
              {
                  Date:"20/JAN/2004",
                  activity:"Lorem ipsum ",
                  details:"Lorem ipsum dolor sit amet,disse vestibulum."
              },
              {
 Date:"12/FEB/2004",
                  activity:"Lorem ipsum dolor sit .",
                  details:"Lorem ipsum d nunc, adipiscing vitae. Ubulum."
              },
              {
                 Date:"12/NOV/2004",
                  activity:"Lorem ipsum dolor.",
                  details:"Lorem ipsum dolor site vestibulum."
              }

            ]

        }

      ],
      all:true,
      unpaid:false,
      paid:false,
      overdue:false,
      count:0
    }
  },
  mutations: {
  
    all(state){
       state.all = !state.all;
      state.unpaid = false
      state.paid = false;
      state.overdue = false
    },
    unPaid(state,payload){
      console.log("Paid")
      state.all = false;
      state.unpaid = !state.unpaid
      state.paid = false;
      state.overdue = false
  // return {...state,unpaid:!state.unpaid,all:!state.all}
   
    },
    paid(state){
        state.all = false;
      state.paid = !state.paid
      state.unpaid = false;
      state.overdue = false
    },

    overdue(state){
      state.all = false;
      state.unpaid = false
      state.paid = false;
      state.overdue = !state.overdue
    }

  },
  actions:{
    

  }
})
</script>

