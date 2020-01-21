<template>
  <div>
   <div class="col-container">
        <!-- <span>
            <input :value="true" type="radio" v-model="isHorizontal">
            <label>Horizontal</label>
        </span>
         <span>
            <input :value="false" type="radio" v-model="isHorizontal">
            <label>Vertical</label>
        </span> -->

        
      <!-- <div class="col-row" v-if="isHorizontal"> -->
        <!-- <span> -->
          <div class="col-row">
              <appTemp  v-for="group in RuleDefinitionComponents.groups" :key="group.name" class="tableCell" :group="group">
              </appTemp>
            </div>
                
            
              <!-- <div class=" tableCell verticallyMiddle" v-if="index < (totalGroups - 1)">
            AND
          </div> -->
          <!-- </div> -->
           <!-- <div class=" tableCell verticallyMiddle" v-if="index < (totalGroups - 1)">
            AND
          </div> -->
        <!-- </span> -->
      <!-- </div> -->


      <!-- <div v-if="!isHorizontal">
        <div  v-for="(group , index ) in RuleDefinitionComponents.groups" :key="group.name">
          <div class="col-row">
            <appTemp class="col" :group="group"></appTemp>
          </div>
          <div  class="col-row verticallyMiddle"  v-if="index < (totalGroups - 1)">
            AND
          </div>
        </div>
      </div> -->

   </div>
  </div>
</template>

<script>
import RuleDefinitionComponents from "./RuleDefinitionComponents.json";
import Temp from "./Temp";

export default {
  name: 'RuleDefinition',
  components:{
    appTemp:Temp,
  },
  data(){
    return {
      isHorizontal:true,
      RuleDefinitionComponents : RuleDefinitionComponents,
    }
  },
  computed: {
    totalGroups() {
      return this.RuleDefinitionComponents.groups.length;
    }
  }
}
</script>

<style scoped>
.verticallyMiddle{
  vertical-align: middle;
}
.tableCell{
    display: table-cell;
}
.col-container {
  display: table;
  border-collapse: separate;
  border-spacing: 1px;
}
.col-row{
    display: table-row; 
}
.col{
    display: table-cell;
}
</style>