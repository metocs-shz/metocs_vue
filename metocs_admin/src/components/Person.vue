<template>
  <div>
    <h2>姓名： {{ person.name }}</h2>
    <h2>年龄： {{ person.age }}</h2>
    <button @click="changePerson">修改名字</button>

    <h2> 一辆汽车: {{ car.name }} , 价格: {{ car.prince }} W </h2>

    <button @click="change">修改价格</button>
    &nbsp;
    <button @click="cleanChange">恢复原价</button>

    <hr/>

    <ul>
      <li v-for="game in games" :key="game.id">{{game.name}}</li>
    </ul>

    <button @click="changeName">修改名称</button>

    <hr/>

    <div>----快乐翻倍计算器-----</div>
    <br>
    <div>
      快乐(A)： <input type="number" v-model="happy_A"><br>
      快乐(B)： <input type="number" v-model="happy_B"><br>
      A*B：  <span>{{res}}</span>
    </div>


  </div>
</template>

<script lang="ts">
export default {
  name: `Person`,
}
</script>

<script setup lang="ts">
import {computed, reactive, ref} from "vue";


   const person = reactive({id:'1',name:'张三',age:"18"})

  function changePerson(){
    person.name = '李四'
  }



  const car = reactive({name:'奔驰',prince: 100 })
  function change() {
    car.prince += 10
  }

  function cleanChange() {
    car.prince = 100
  }


  // 列表

  const games = reactive([
    {id:"1",name:'英雄联盟'},
    {id:'2',name:'战地'},
    {id:"3",name:'守望先锋'},
  ])

  function changeName() {
    games[0].name = "快乐启动"
  }

  const happy_A = ref(0)
  const happy_B = ref(0)

  const res = computed(()=>{
    console.log("---------")
    return happy_A.value * happy_B.value
  })




</script>
<style scoped>

li {
  font-size: 20px;
}

</style>
