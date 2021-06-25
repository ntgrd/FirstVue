<template>
<div>
     <div class="display">
       <input type='number' v-model.number.trim="operand1"/>
       <input type='number' v-model.number.trim="operand2"/>
       = {{result}}
     </div>

     <div class="keyboard">
   <button v-on:click="result = operand1 + operand2">+</button>
   <button v-on:click="result = operand1 - operand2">-</button>
   <button @click="divide">/</button>
   <button @click="mult">*</button>
   <button @click="pow">pow</button>
   <button @click="integerDiv">%</button>
 </div>

  </div>

</template>
 
<script>
 export default {
   name: 'Calculator',
   data(){
       return {
           operand1: 0,
           operand2: 0,
           result: 0
       }
   },
   methods:{
        mult(){
            this.result = this.operand1 * this.operand2
        },
        divide(){
            if (this.operand2 == 0)
                console.log('error');
            this.result = this.operand1 / this.operand2
        }, 
        pow(){
            this.result = Math.pow(this.operand1, this.operand2)  
        },    
        integerDiv(){
            if (this.operand2 == 0)
                console.log('error');
            this.result = Math.floor(this.operand1/this.operand2)  
        },   
    },
}
</script>


<style lang="scss">
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
