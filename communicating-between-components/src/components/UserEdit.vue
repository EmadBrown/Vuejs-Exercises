<template>
    <div class="component">
        <h3>You may edit the User here</h3>
        <p>Edit me!</p>
        <p>User Age: {{age}}</p>
        <button @click="editAge">Edit Age</button>
        <button @click="editAgeEventBus">Edit Age Event Bus</button>
        <br>
          <button @click="changeAgeBusOpject">Change Age Bus Opject</button>
    </div>
</template>

<script>
import {eventBus} from '../main'
export default{
    props:['age'],
    methods:{
        editAge(){
            this.age = 30;
            this.$emit('ageWasEdited', this.age)
        },
        editAgeEventBus(){
            this.age = 28;
            eventBus.$emit('ageWasEditedEventBus', this.age)
        },
         changeAgeBusOpject(){
            this.age = 30;
            eventBus.changeAge(this.age)
        }
    },
}
</script>

<style scoped>
    div {
        background-color: lightgreen;
    }
</style>
