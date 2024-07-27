<script setup>
import { ref } from 'vue'

defineProps({
  msg: String,
})

const count = ref(0)
const count1 = ref(0)//setup直接定义变量
const user = ref(
    {
      name: 'John Doe',
      age: 30
    }
)
const url = 'https://github.com/bevyengine/bevy?utm_source=gold_browser_extension'
const imageSrc = 'https://github.com/Debulin/picx-images-hosting/raw/master/vuelearn/test.13loeumuwh.webp'
const htmlContent = '<p>This is <strong>HTML</strong> content.</p>'
const incr = () => {//setup直接定义方法
  count1.value++
}
const onInput = (e) => {
  text.value=e.target.value
}
const text = ref('测试')

const update = () => {
  user.value.name = 'Jane Doe'
  user.value.age = 20
}
</script>

<template>
  <h1>{{ msg }}</h1>
  <div>
    <p>
      {{count1}}
    </p>
    <p>
      User's name: {{ user.name }}
    </p>
    <p>
      User's age: {{ user.age }}'
    </p>
    <img v-bind:src="imageSrc" alt="testImage">
    <p></p>
    <a v-bind:href="url">Rust Bevy Engine</a>
    <p></p>
    <button @click = "incr">
      Increment func
    </button>
    <p></p>
    <div v-html="htmlContent"></div>
    <div>
      <input v-bind:value="text" v-on:input="onInput" placeholder="Type here">
      <p>{{text}}</p>
    </div>
    <button @click = "update">
      Update User Info
    </button>
  </div>

  <div class="card">
    <button type="button" @click="count++">count is {{ count }}</button>
    <p>
      Edit
      <code>components/HelloWorld.vue</code> to test HMR 原来是实时的吗
    </p>
  </div>

  <p>
    Check out
    <a href="https://vuejs.org/guide/quick-start.html#local" target="_blank"
      >create-vue</a
    >, the official Vue + Vite starter
  </p>
  <p>
    Learn more about IDE Support for Vue in the
    <a
      href="https://vuejs.org/guide/scaling-up/tooling.html#ide-support"
      target="_blank"
      >Vue Docs Scaling up Guide</a
    >.
  </p>
  <p class="read-the-docs">Click on the Vite and Vue logos to learn more</p>
</template>

<style scoped>
.read-the-docs {
  color: #888;
}
</style>
