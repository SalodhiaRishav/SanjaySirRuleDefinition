<template>
   <div style="display:flex" >
       <div class="border-1">
            <div class = "radioButtons">
                <div>
                    <input value="and" type="radio" v-model="group.operation">
                    <label>AND</label>
                </div>
                <div>
                    <input value="or" type="radio" v-model="group.operation">
                    <label>OR</label>
                </div>
            </div>

            <div class = "inputs">
                <div v-for="property in group.properties" :key="property.value" >
                    <label class="displayBlock">{{property.name}}</label>
                    <input class="margin-4 displayBlock"  v-for="index in property.propertyCount" v-model="property.values[index-1]" :key="index" :type="property.type">
                </div>
                <div>
                    <button @click="addInputs">+</button>
                </div>
            </div>
       </div>
       <slot >

       </slot>
    </div>
</template>

<script>
export default {
  props:{
     group: {
      type: Object,
    },
  },
  methods:{
      addInputs(){
          for(let i =0 ;i<this.group.properties.length;++i)
          {
              this.group.properties[i].propertyCount++;
          }
      }
  }  
}
</script>

<style scoped>
.inputs{
    display: flex;
}
.radioButtons{
    display: flex;
    justify-content: flex-end;
}
.border-1{
    border: 1px solid black;
    padding: 4px;
}
.groupBox{
    display: flex;
}
.margin-4
{
    margin:4px;
}
.displayBlock{
    display: block;
}
.displayInlineBlock{
    display: inline-block;
}

</style>