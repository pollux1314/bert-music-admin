<script setup>
import { ref } from 'vue'
import { sayHello } from '../api/hello'
// defineProps({
//   msg: String
// })

const count = ref(0)
const message = ref('波特音乐盒')

const hi = () => {
  // message.value="已请求"
  sayHello().then(res => {
    message.value = res.data
    console.log(res)
  })
}
</script>

<template>
  <h1>{{ message }}</h1>
  <q-btn color="primary" @click="count++"> 点击次数{{ count }} </q-btn>
  <br />
  <br />
  <q-btn color="primary" @click="hi"> hi </q-btn>
</template>

<style scoped></style>
