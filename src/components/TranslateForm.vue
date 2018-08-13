<template>
    <div id="translateForm">
        <form v-on:submit="formSubmit">
            <input type="text" v-model="textToTranslate" placeholder="Enter a word">
            <input type="submit" value="Translate">
            <select v-model="language">
                <option value="fr">French</option>
                <option value="zh">Chinese</option>
                <option value="es">Spanish</option>
                <option value="th">Thai</option>
                <option value="pt">Portuguese</option>
            </select>
        </form>
    </div>
</template>

<script>


export default {
    name: 'translateForm',
    data(){
        return {
            textToTranslate: '',
            language: '',
        }
    },
    created(){
        //add Thai and Portuguese
        this.language = "fr";
    },
    methods: {
        formSubmit(e){
            this.$emit('formSubmit', this.textToTranslate, this.language);
            e.preventDefault(); //prevents the default submit
        }
    }

}
</script>

<style>

</style>
