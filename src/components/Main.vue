<template>
    <div class="app">
        <div class="maintext">
            <h1>Yes / No</h1>
            <h2>{{this.answer}}</h2>
            <h3>Вопрос оканчивается на "?"</h3>
            <input v-model="que">
        </div>
    </div>
</template>

<script>
    export default {
        data(){
            return{
                que:'',
                answer:'',
            }
        },
        watch: {
            // эта функция запускается при любом изменении вопроса
            que:function () {
                this.answer = "Ожидаю, когда вы закончите печатать..";
                if(this.que.endsWith('?')){
                    this.answer = Math.random() < 0.5 ? 'Да' : 'Нет';
                }
                else if(this.que === ""){
                    this.answer = '';
                }
            }
        },
    }
</script>
<style>
    h1 {
        font-family: Avenir, Helvetica, Arial, sans-serif;
        font-size: 5em;
        text-align: center;
        padding-top: 100px;
    }
    h2 , h3{
        font-family: Avenir, Helvetica, Arial, sans-serif;
        font-size: 2.5em;
        text-align: center;
    }
    input{
        font-family: Avenir, Helvetica, Arial, sans-serif;
        font-size: 2em;
        margin-top:100px;
        margin-left:750px;
    }
</style>