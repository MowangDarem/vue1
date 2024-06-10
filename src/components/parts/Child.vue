<template>
    <div>
        <p>子组件</p>
        <p>{{ msg }}</p>
        <p>{{ msg1 }}</p>
        <p><button @click="test('成功')">测试button</button></p>
        <p><button @click="changs()">修改父组件传递的值</button></p>
    </div>
</template>

<script>
export default {
    // props数组方式接收属性
    // props:["msg","msg1","test"]
    // props对象方式接收，推荐使用
    props: {
        // 表示接收的msg是一个string类型
        msg: String,
        msg1: {
            type:[Number,String],
            // 没有接收到msg1值时，会使用default值，即缺省值
            // default:"初始值"
            // 加了required：true表示父组件必须要传msg1
            // required:true
            // 自定义校验使用validator方法
            // 参数为接收到的msg1的值
            // 返回值如果为true，则校验通过
            // 否则不通过
            validator(val){
               return (val>=0 &&val<=150)
            }
        },
        test: Function
    },
    methods:{
        changs(){
            this.$emit("changs",45)
        }
    }

}
</script>

<style lang="less" scoped></style>