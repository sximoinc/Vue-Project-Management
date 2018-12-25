<template>
  <div>
  <Tabs prop="tabl-3"></Tabs>
  <div class="container">
   
    <v-card flat class="mb-3">
     

          <v-toolbar card prominent color="white">
           <v-btn  color="indigo" dark small>
              <span> Create new Task </span> 
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


          <v-card-text>
            <v-layout row wrap grid-list-sm class="mb-1">
              <v-flex xs12 sm3>
                  <v-card  color="" class="elevation-0 mr-1">
                    <v-card-text>
                          <h1 class="display-1">3</h1>
                          <p>Not Started <br />
                          <span>Tasks assigned to me: 4 </span></p>

                    </v-card-text>
                  </v-card>
              </v-flex>
              <v-flex xs12 sm3>
                  <v-card  color="" class="elevation-0 mr-1">
                    <v-card-text>
                            <h1 class="display-1">0</h1>
                          <p>In Progress<br />
                          <span>Tasks assigned to me: 4 </span></p>

                    </v-card-text>
                  </v-card>
              </v-flex>
              <v-flex xs12 sm3>
                  <v-card  color="" class="elevation-0 mr-1">
                    <v-card-text>
                          <h1 class="display-1">2</h1>
                          <p>Awaiting Feedback<br />
                          <span>Tasks assigned to me: 4 </span></p>
                    </v-card-text>
                  </v-card>
              </v-flex>
              <v-flex xs12 sm3>
                  <v-card  color="" class="elevation-0 mr-1">
                    <v-card-text>
                          <h1 class="display-1">54</h1>
                          <p>Complete<br />
                          <span>Tasks assigned to me: 4 </span></p>
                    </v-card-text>
                  </v-card>
              </v-flex>

            </v-layout>
          </v-card-text>

      </v-card>    
      <v-card flat>    
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
              text: 'Task Name',
              align: 'left',
              sortable: false,
              value: 'name'
            },
            { text: 'Projects', value: 'customer' },
            { text: 'Tags', value: 'tags' },
            { text: 'Start', value: 'start' },
            { text: 'End', value: 'end' },
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
