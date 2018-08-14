<template>
    <div class="container">
        <div id="translateOuput" style="width: 100px; background-color: red;">
            <span>{{translatedText}}</span>
        </div>
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
    }
}
</script>

<style>
    #translateOutput {
        border-radius: 10px;
        border: 1px #ccc solid;
        background-color:lightgray;
        padding: 10px;
    }
</style>
