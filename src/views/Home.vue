<template>
  <div class="home">
    <img alt="Vue logo" src="../assets/logo.png">
    <h1>Home Page</h1>

    <h4>my name is {{ name }} - my age is {{ age }}</h4>
    <button @click="sayHello">Hello</button>
  </div>
</template>

<script>
export default {
    name: 'Home',

  setup() {
    // My data:
    let name = "Khelifa"
    let age = 28
    // Methods: 
    const sayHello = () => console.log("Welcome in prostam")

    return{
      name,
      age,
      sayHello
    }
  },
 
 
}
</script>
