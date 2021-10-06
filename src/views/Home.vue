<template>
  <div class="home">
    <img alt="Vue logo" src="../assets/logo.png">
    <h1  ref="title">Home Page</h1>

    <p>{{ socite.name }}</p>

    <h4>my name is {{ name }} - my age is {{ age }}</h4>
    <button @click="sayHello">Hello</button>
        <button @click="age++">inc</button>

  </div>
</template>

<script>
import { reactive, ref } from 'vue'
export default {
    name: 'Home',

  setup() {
    // My data:
    let name = ref("Khelifa")
    let age = ref(28)
    let title = ref(null);

    let socite = reactive({
        name: "PROSTAM",
        siret: "94875856"
    });
    // Methods: 
    const sayHello = () => {
      console.log("Welcome in prostam")
      title.value.textContent = "Salem"
      title.value.classList.add("text-end")
      name.value = "Sabah"
      socite.name = "SASU PROSTAM"
    }

    return{
      name,
      age,
      title,
      sayHello,
      socite
    }
  },
 
 
}
</script>
