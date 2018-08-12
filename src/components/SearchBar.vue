<template>
    <div>
        <input @input="onInput"/>
    </div>
</template>

<script>
    export default {
    name:'SearchBar',
    methods: {
        onInput : function(event){
           this.$emit('termsChange',event.target.value);
        }
                
    },
    }
    
</script>

<style scoped>

</style>