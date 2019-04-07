<template>
    <div class="children-box">
        <h4 :style="{color:value.theme}">我是子元素</h4>
        <div @click="changeValue">改颜色</div>
    </div>
</template>
<script>
    export default {
        inject: {
            value:{
                from:'test',
                default:()=>{}
            }
        },
        methods:{
            changeValue(){
                this.value.theme = 'red'
            }
        }
    }
</script>
<style scoped>
    .children-box {
        border:1px solid greenyellow;
    }
</style>