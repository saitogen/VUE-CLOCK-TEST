<template>
ClockScreenを表示します
</template>
<script>
    export default{
        name:"ClockScreen",
        date(){
            return{
                // 現在の時刻を取得
                date:new Date(),
            };
        },
        computed:{
            // 年
            year(){
                return this.date.getFullYear();
            },
            month(){
                return this.date.getMonth()+1;
            },
            day(){
                return this.dateTimePadding(this.date.getDate());
            },
            hour(){
                return this.dateTimePadding(this.date.getHours());
            },
            minutes(){
                return this.dateTimePadding(this.date.getMinutes());
            },
            sec(){
                return this.dateTimePadding(this.date.getSeconds());
            },
        },
        mounted:{
            // 現在日時をセット
            
            // 一秒ごとにseDate()を実行
        },
        methods:{
            // 日時を二桁に変換
            dateTimePadding(num){
                return ("0"+num).slice(-2);
            },
            // 現在の日時をセット
            setDate(){
                this.date=new Date();
            }
        },
    };
</script>
<style>
</style>