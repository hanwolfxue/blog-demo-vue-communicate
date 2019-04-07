<template>
    <div class="children-box">
        <h4>我是子元素</h4>
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
        created(){
            Bus.$on('setMsg',val=>{
                this.msg = val
            })
        },
    }
</script>
<style scoped>
    .children-box {
        border:1px solid greenyellow;
    }
</style>