<template>
  <div class="home">
    <img alt="Vue logo" src="../assets/logo.png">
    <h1  ref="title">Home Page</h1>

    <h4>my name is {{ name }} - my age is {{ age }}</h4>
    <button @click="sayHello">Hello</button>
  </div>
</template>

<script>
import { ref } from 'vue'
export default {
    name: 'Home',

  setup() {
    // My data:
    let name = "Khelifa"
    let age = 28
    let title = ref(null);
    // Methods: 
    const sayHello = () => {
      console.log("Welcome in prostam")
      title.value.textContent = "Salem"
      title.value.classList.add("text-end")
    }

    return{
      name,
      age,
      title,
      sayHello
    }
  },
 
 
}
</script>
