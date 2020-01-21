<template>
  <div id="app">
    <appRuleDefinition></appRuleDefinition>
  </div>
</template>

<script>
import RuleDefinition from './components/RuleDefinition2.vue'

export default {
  name: 'app',
  components: {
    appRuleDefinition : RuleDefinition
  }
}
</script>

<style>
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  font-size: 12px;
  margin-top: 60px;
}
</style>
