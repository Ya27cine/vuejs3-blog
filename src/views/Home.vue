<template>
  <div class="home">
    <img alt="Vue logo" src="../assets/logo.png">
    <h1  ref="title">Home Page</h1>

    <p>{{ socite.name }}</p>

    <h4>my name is {{ name }} - my age is {{ age }}</h4>
    <button @click="sayHello">Hello</button>
        <button @click="age++">inc</button>
  <hr>
    <input type="text" name="" v-model="search">
    <div v-for="course in result">
         {{ course}}
    </div>
  </div>

  <hr>
  <button @click="handWatch">Stop Watch</button>
</template>

<script>
import { reactive,computed, ref,  watchEffect, watch } from 'vue'
export default {
    name: 'Home',

  setup() {
    // My data:
    const courses = ref(['Laravel', 'Symfony', 'ReactJS', 'VueJs', 'NodeJs', "JavaEE", 'Angular', "Flesk", 'CakePhp']);
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

        // computed 
    const search = ref('');
    const result  = computed( () => {
                  return courses.value.filter( course => course.includes(search.value) )
    });


    // watch
    const stopWatch   = watch(search, () => console.log(' watch : '+search.value))
    const stopWatchEff =  watchEffect( () => console.log(' watchEffect : '+search.value))

     const handWatch = () => {
        stopWatch();
        stopWatchEff();
    }

    return{
      name,
      age,
      title,
      sayHello,
      socite,
      result,
      search,
      handWatch
    }
  },
 
 
}
</script>
