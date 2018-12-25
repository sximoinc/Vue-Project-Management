<template>
<div>
  <Tabs prop="tabl-1"></Tabs>
  <div class="container">

    <v-tabs
            
            color="grey lighten-3"           
            class="mb-0"
            centered
            v-model="selected_tab"
          >
           <v-tabs-slider color="indigo"></v-tabs-slider>

            <v-tab  :to="'/projects/projects'">
              All Projects             
            </v-tab>
            <v-tab :to="'/projects/projects'">
                My Projects               
            </v-tab>
              
             
        </v-tabs> 

    <v-card v-for="project in items" class="mb-2" flat>
          
          <v-card-text>
            <v-layout row wrap grid-list-sm class="mb-1">
                <v-flex xs12 sm1 class="text-xs-center">
                    <v-icon size="72" >apps</v-icon>
                </v-flex>
               <v-flex xs12 sm11 >

                <v-toolbar card  color="transparent" class="pa-0">
                  <v-toolbar-title> {{ project.project }} </v-toolbar-title>
                   

                    <v-spacer></v-spacer>
                    
                    <v-btn icon>
                      <v-icon>more_vert</v-icon>
                    </v-btn>
                  </v-toolbar>

                    <v-layout row wrap>
                        <v-flex xs12 sm6>
                            <p> {{ project.description }} </p>

                              <h5> Progress :  </h5>
                             <v-progress-linear label="Progress"
                              color="primary"
                              height="5"
                              :value="project.progress"
                            ></v-progress-linear>

                            <div class="">
                              <v-chip small outline @click="">                                   
                                General Discussion
                              </v-chip>
                              <v-chip small outline @click="">                                   
                                Customizataion
                              </v-chip>
                              <v-chip small outline @click="">                                   
                                Request
                              </v-chip>
                              <v-chip small outline @click="">                                   
                                Report Bug
                              </v-chip>
                            </div>
                        </v-flex>
                        <v-flex xs12 sm6>
                          <h4> Teams </h4>
                          <div class="pl-2">
                            <v-avatar v-for="(t,index) in 5" size="30" class="mr-2 mb-2">
                              <img :src="img_url +'uploads/contacts/'+index+'.jpg'" alt="avatar">
                            </v-avatar>
                          </div>  

                        </v-flex>
                    </v-layout>
                    

                    

               </v-flex>
               
              

            </v-layout>
        </v-card-text>
    </v-card>            
    
    
  </div>
</div>  
</template>
<script>
import axios from 'axios'
import {store} from '../../store'
import moment from 'moment'
import PulseLoader from 'vue-spinner/src/PulseLoader.vue'
import Tabs from './Tabs'
  export default {
    $_veeValidate: {
      validator: 'new'
    },
    name: 'Sv_CRUD',
    components: {
      PulseLoader,
      Tabs
    },    
     data () {
        return {
         
          headers: [
            {
              text: 'Project Name',
              align: 'left',
              sortable: false,
              value: 'project'
            },
            { text: 'Customers', value: 'customer' },
          
            { text: 'Start', value: 'start' },
            { text: 'End', value: 'end' },
            { text: 'Members', value: 'members' },
            { text: 'Status', value: 'status' }
          ],
           items : [] ,
            img_url : store.state.baseUrl,
        /* END Dinamic Data From CRUDENGINE */        
        //status_active: true   
          baseUrl : store.state.baseUrl +'projects/projects'
        
        }
    },    
    mounted: function () 
    {
       this.getData()
          
    },
    methods : {
     
      getData() {

        this.items = [
            { project : 'SEO Optimazation' , description : 'A full-featured Webpack + vue-loader setup with hot reload, linting, testing & css extraction.' ,  customer : 'Sximo Inc' ,start : '21/09/18' , end : '25/09/18' , members : '', status : 'inprogress' , progress: 50 } ,
            { project : 'Redesign Web' , description : 'A full-featured Webpack + vue-loader setup with hot reload, linting, testing & css extraction.' , customer : 'JB Consultant' ,start : '21/09/18' , end : '25/09/18' , members : '', status : 'inprogress' , progress: 85 } ,
            { project : 'Convert to Mobile' ,description : 'A full-featured Webpack + vue-loader setup with hot reload, linting, testing & css extraction.' ,  customer : 'WorldBank LTD' ,start : '21/09/18' , end : '25/09/18' , members : '', status : 'inprogress' , progress: 35 } ,
            { project : 'Android & Ios App' , description : 'A full-featured Webpack + vue-loader setup with hot reload, linting, testing & css extraction.' ,  customer : 'American Express' ,start : '21/09/18' , end : '25/09/18' , members : '', status : 'inprogress' , progress: 45 } ,
            { project : 'SEO Optimazation' ,  description : 'A full-featured Webpack + vue-loader setup with hot reload, linting, testing & css extraction.' ,  customer : 'Sximo Inc' ,start : '21/09/18' , end : '25/09/18' , members : '', status : 'inprogress' , progress: 70 } , 

        ]

      }

    }

}
</script>
