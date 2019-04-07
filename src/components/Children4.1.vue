<template>
    <div class="children-box">
        <h4>我是子元素B</h4>
        <p>{{value1}}</p>
        <button @click="clickEvent">改变value1的值</button>
        <Children42 v-bind="$attrs" v-on="$listeners"></Children42>
    </div>
</template>
<script>
    import Children42 from './Children4.2'
    export default {
        name:'Children41',
        inheritAttrs:false,
        props:['value1'],
        components:{
            Children42
        },
        methods:{
            clickEvent(){
                this.$emit('clickEvent1')
            }
        },
    }
</script>
<style scoped>
    .children-box {
        border:1px solid greenyellow;
    }
</style>