<script>
export default {
  props : ["archetypeList"],

  data(){
    return{
      archetypeValue : this.archetypeList[0],
    }
  },
  methods:{
  },
}
</script>

<template>
   <select name="archetype-selector" id="archetype-selector" v-model="archetypeValue" @change="$emit('getOptions', archetypeValue)">
     <option v-for="archetype in archetypeList" :value="archetype">{{ archetype }}</option>
   </select>
</template>

<style lang="scss">
  
</style>