<template>
    <div style="display:flex;">
        
        <form-template style="flex:3;"></form-template>

        <div style="flex:1;"></div>
       
    </div>
</template>

<script>
import Form from './form-template'
import { bus } from "../main";

export default {
    components: {
        'form-template': Form
    },
}
</script>

<style scoped>
 

</style>