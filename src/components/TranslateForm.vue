<template>
    <div class="container">
        <div id="translateForm">
            <div>
                <form id="transForm" v-on:submit="formSubmit" >
                    <input class="form-control" type="text" v-model="textToTranslate" placeholder="Enter a word in English">
                    <select class="form-control" v-model="language">
                        <option value="fr">French</option>
                        <option value="zh">Chinese</option>
                        <option value="es">Spanish</option>
                        <option value="th">Thai</option>
                        <option value="pt">Portuguese</option>
                    </select>
                    <input type="submit" class="btn" value="Translate">
                </form>
            </div>
        </div>
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
    select{
        margin-top: 10px;
    }
    .btn {
        margin-top: 20px !important;
        margin-bottom: 10px;
        background-color: #317EC6;
        /* border: 2px #317EC6 solid !important; */
    }
    #transForm {
        border-radius: 10px;
        border: 2px #317EC6 solid;
        background-color:#3E99ED;
        padding: 10px;
    }
</style>
