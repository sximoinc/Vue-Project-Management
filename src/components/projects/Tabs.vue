<template>
 	<div>
    	<v-tabs
            
            color="white"
           
            class="mb-0"
            centered
            v-model="selected_tab"
          >
           <v-tabs-slider color="indigo"></v-tabs-slider>

            
            <v-tab :to="'/projects/projects'">
                Projects
               
              </v-tab>
              <v-tab :to="'/projects/pm_tasks'">
                Tasks / Activities
               
              </v-tab>
              <v-tab :to="'/projects/pm_issues'">
                Issue Trackers
               
              </v-tab>
              <v-tab :to="'/crm/crm_report'">
                Sources
               
              </v-tab>
             
        </v-tabs>   

              
  </div>
</template>
<script>
import axios from 'axios'
import {store} from '../../store'
import moment from 'moment'
import PulseLoader from 'vue-spinner/src/PulseLoader.vue'
  export default {
    $_veeValidate: {
      validator: 'new'
    },
    name: 'Sv_CRUD',
    components: {
      PulseLoader
    },  
     props: {
            selected_tab : String
        },  
     data () {
       
        return {
          
        
        }
    },    
    mounted: function () 
    {
       
          
    },
    methods : {
     


    }

}
</script>
<style type="text/css">
	.v-tabs__item {
		font-size: 11px;
	}
</style>
