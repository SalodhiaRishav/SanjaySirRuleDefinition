<template>
  <div class="groupBox">
    <div class = "radioButtons" align="right">
        <span >
            <input value="and" type="radio" v-model="group.operation">
            <label>AND</label>
        </span>
         <span>
            <input value="or" type="radio" v-model="group.operation">
            <label>OR</label>
        </span>
    </div>
    <div class = "inputs displayInlineBlock">
        <div class="displayInlineBlock inputGroup" v-for="property in group.properties" :key="property.value">
            <label class="displayBlock">{{property.name}}</label>
            <input v-for="index in inputCounts" :key="index" :type="property.type" class="displayBlock inputComponent">
        </div>
        <div class="displayInlineBlock inputGroup" >
            <button class="displayBlock" @click="addInputs">ADD</button>
        </div>
    </div>
  </div>
</template>

<script>
export default {
  props:{
     group: {
      type: Object,
    },
  },
  data(){
        return {
            inputCounts:1,
        }
    },
  methods:{
      addInputs(){
          this.inputCounts+=1;
      }
  }  
}
</script>

<style scoped>
.groupBox{
    border: 1px solid black;
    padding: 4px;
}
.inputGroup
{
    margin:4px;
}
.displayBlock{
    display: block;
}
.displayInlineBlock{
    display: inline-block;
}
.inputComponent{
    margin-bottom: 4px;
}
.col-container {
  display: table;
  width: 100%;
}
.col {
  display: table-cell;
  padding: 16px;
}

</style>