<template>
    <div class="children-box">
        <h4>我是子元素</h4>
        <input type="text" v-model="msg">
        <p>通过总线方式通信 {{msg}}</p>

    </div>
</template>
<script>
    import Bus from '../bus'
    export default {
        data(){
            return {
                msg:'hello world'
            }
        },
        mounted() {
        },
        watch:{
            msg:function (newVal) {
                Bus.$emit('setMsg',newVal)
            },
        }
    }
</script>
<style scoped>
    .children-box {
        border:1px solid greenyellow;
    }
</style>