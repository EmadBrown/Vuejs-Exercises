<template>
    <div class="component">
        <h3>You may view the User Details here</h3>
        <p>Many Details: {{name}}</p>
        <p>User Age: {{userAge}}</p>
        <p>Many Details reverse: {{reverseName()}}</p>
        <button @click="resetName">Reset name</button>
        <button @click="resetFunction()">Reset Function</button>
    </div>
</template>

<script>
import {eventBus} from '../main'
export default{
    props:{
        name:{
            type: String,
            required: true,
        },
        resetFunction: Function,
        userAge: Number
    },
    methods:{
        reverseName(){
            return this.name.split('').reverse().join('')
        },
        resetName(){
            this.name = 'Emad'
            this.$emit('nameIsReset', this.name) 
        }
    },
     created (){
         eventBus.$on('ageWasEditedEventBus', (age)=>{
             this.userAge = age
         });
          eventBus.$on('ageWasEditedEventBusOpjectFunction', (age)=>{
             this.userAge = age
         });
         
    }
}
</script>

<style scoped>
    div {
        background-color: lightsteelblue;
    }
</style>
