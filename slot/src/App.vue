<template>
    <div class="container">
        <div class="row">
            <div class="col-xs-12">
                <br>
                <button class="btn btn-primary" @click="switchComponent = 'appBlue', color = 'Bule'">Load Blue Template</button>
                <button class="btn btn-success" @click="switchComponent = 'appGreen', color = 'Green'">Load Green Template</button>
                <button class="btn btn-danger"  @click="switchComponent = 'appRed', color = 'Red'">Load Red Template</button>
                <hr>
                <component :is="switchComponent">
                    <h2>Load {{color}} Template</h2>
                </component>
            </div>
        </div>
    </div>
</template>

<script>
    import Blue from './components/Blue.vue';
    import Green from './components/Green.vue';
    import Red from './components/Red.vue';

    export default {
        data :  function(){
            return {
               switchComponent : 'appBlue',
               color: 'Blue'
            }
        },
        components: {
            appBlue: Blue,
            appGreen: Green,
            appRed: Red
        }
    }
</script>

<style>
</style>
