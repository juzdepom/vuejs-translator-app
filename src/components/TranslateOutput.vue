<template>
    <div id="translateOuput">
        <h2>{{translatedText}}</h2>
    </div>
</template>

<script>


export default {
    name: 'translateOuput',
    props:['translatedText'],
    data(){
        return {
            textToTranslate: '',
        }
    },
    methods: {
        // formSubmit(e){
        //     this.$emit('formSubmit', this.textToTranslate);
        //     e.preventDefault(); //prevents the default submit
        // }
    }

}
</script>

<style>

</style>
