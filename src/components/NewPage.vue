<template>
    <div class='helloworld'>
        {{ msg2 }}
    </div>
</template>
<script>
    export default{
        name:'helloworld',
        props:{
            msg:String,
            msg2:String
        }
    }
</script>