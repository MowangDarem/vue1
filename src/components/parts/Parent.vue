<template>
    <div>
        <p>父组件</p>
        <!-- 传变量和方法需要使用v-bind来绑定 -->

        <!-- @changs 监听事件 -->
        <Child ref="ref1" msg="传递死数据" :msg1="msgVar" :test="test1" @changs="changm1"></Child>
        <p ref="ref2">123123</p>
        <p><button @click="ch()">点击获取</button></p>
        <p ref="ref3">田某人写的hello wolrd</p>
    </div>
</template>

<script>
import Child from "./Child.vue"
export default {
   components:{
    Child
   },
   data(){
    return{
        msgVar:90
    }
   },
   methods:{
    test1(str){
        alert("测试方法" +str)
    },
    changm1(val){
        this.msgVar=val;
    },
    ch(){
        console.log(this);
        console.log(this.$refs.ref1.msg)
        
    }
   }
}
</script>

<style lang="less" scoped></style>