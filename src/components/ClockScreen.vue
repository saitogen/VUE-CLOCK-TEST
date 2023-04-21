<template>
    <div class="container">
        <div class="clock">
            <div class="date">
            <p>{{ year }}/{{ month }}/{{ day }}</p>
            </div>
            <div class="time">
                <p>
                    {{ hour }}:{{ minutes }}<span class="seconds">:{{ seconds }}</span>
                </p>
            </div>
        </div>
    </div>
</template>
<script>
    export default{
        name:"ClockScreen",
        data(){
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
            seconds(){
                return this.dateTimePadding(this.date.getSeconds());
            },
        },
        mounted(){
            // 現在日時をセット
            this.setDate();
            // 一秒ごとにseDate()を実行
            setInterval(()=>this.setDate(),1000);
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
<style scoped>
    .container{
        height: 100%;
        display: flex;
        flex-flow: column;
        justify-content: center;
        align-items: center;
        background-color: black;
    }
    p{
        margin: 0px;
    }
    .date,
    .time{
        font-weight:700 ;
        color: #00ff01;
    }
    .date{
        font-size: 70px;
        text-align: right;
    }
    .time{
        font-size: 70px;
    }
    .seconds{
        font-size: 30px;
    }
</style>