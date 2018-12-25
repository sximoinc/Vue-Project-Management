<template>
<div>
  <Tabs prop="tab-4"></Tabs>
  <div class="container">
   
    <v-card flat>
                <v-toolbar card prominent color="white">
           <v-btn  color="indigo" dark small>
              <span> Create new </span> 
            </v-btn>

            <v-spacer></v-spacer>
             <v-autocomplete prepend-icon="filter_list" placeholder="Projects " ></v-autocomplete>
             <v-autocomplete  item-key="value" item-text="text" prepend-icon="filter_list" placeholder="Assign To : "  ></v-autocomplete>
            
            <v-spacer></v-spacer>
            
             
            <v-btn icon>
              <v-icon>apps</v-icon>
            </v-btn>

            <v-btn icon>
              <v-icon>more_vert</v-icon>
            </v-btn>

            
          </v-toolbar>
          <v-divider></v-divider>
        <v-card-text >
            

              <v-data-table
                  :headers="headers"
                  class="elevation-0"
                ></v-data-table>   

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
              text: 'Issues Title',
              align: 'left',
              sortable: false,
              value: 'name'
            },
            { text: 'Tasks', value: 'customer' },
            { text: 'Projects', value: 'tags' },
            { text: 'Assigned to', value: 'members' },
            { text: 'Status', value: 'status' }
          ],
        /* END Dinamic Data From CRUDENGINE */        
        //status_active: true   
          baseUrl : store.state.baseUrl +'projects/projects'
        
        }
    },    
    mounted: function () 
    {
       
          
    },
    methods : {
     


    }

}
</script>
