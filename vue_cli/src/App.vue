<template>
  <h2>一个人信息</h2>
  <h2>姓名:{{name}}</h2>
  <h2>年龄:{{age}}</h2>
  <button @click="sayHello">说话</button>
  <button @click="changeInfo"></button>
</template>

<script>
import {h} from "vue"

//引入ref函数
import {ref} from 'vue'

export default {
  name: 'App',
  setup(){
    //数据
    let name = ref('张三')
    let age = ref(18)
    let job = ref({
      type:'前端工程师',
      salary:'30k'
    })

    //方法
    function sayHello(){
      alert(`我叫${name},我${age}岁了，你好啊!`)
    }
    // return {
    //   name,age,sayHello
    // }

    function changeInfo(){
      name.value = "李四"
      age.value = 20
    }

    //返回一个函数(渲染函数)
    // return ()=>h('h1','尚硅谷')
    return {
      name,
      age,
      changeInfo
    }
  }
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
