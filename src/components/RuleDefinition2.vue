<template>
<div>
        <span>
            <input :value="true" type="radio" v-model="isHorizontal">
            <label>Horizontal</label>
        </span>
         <span>
            <input :value="false" type="radio" v-model="isHorizontal">
            <label>Vertical</label>
        </span>
    <div class="horizontolFlexContainer" v-if="isHorizontal">
       <appTemp2   :group="group" v-for="(group,index) in RuleDefinitionComponents.groups" :style="'order: '+group.order"  :key="group.name">     
         <div style=" align-self: center;margin:2px" v-if="index < (totalGroups-1)">AND</div>
       </appTemp2>
   </div>
    <div class="verticalFlexContainer" v-if="!isHorizontal">
       <appTemp2  :group="group" v-for="(group,index) in RuleDefinitionComponents.groups" :style="'order: '+group.order" :key="group.name">     
         <div style="  justify-content: center;: center;margin:2px" v-if="index < (totalGroups-1)">AND</div>
       </appTemp2>
   </div>
   <pre>{{RuleDefinitionComponents}}</pre>
</div>
 
</template>

<script>
import RuleDefinitionComponents from "./RuleDefinitionComponents.json";
import Temp2 from "./Temp2";

export default {
  name: 'RuleDefinition',
  components:{
    appTemp2:Temp2,
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
.horizontolFlexContainer{
     display: flex;
     flex-wrap: nowrap;
     margin:10px;
}
.verticalFlexContainer{
     display: flex;
     flex-direction: column;
     flex-wrap: nowrap;
     margin:10px;
}
</style>