<template>
  <div class="home">
    <div ref="p">  Mon nom est {{ firstname }} {{ lastname }}</div>
  
    <p>{{ fullname }} </p>
    <p>{{ age }} </p>

    <div><input type="text" v-model="firstname"></div>
    
    <button @click="add">Add</button>

    <button @click="age++">Add</button>

    <button @click="addDate">addDate</button>

       <p>{{ name_and_age.name }} </p>
        <p>{{ name_and_age.date }} </p>

  </div>
</template>

<script>

  import { ref } from "vue";

export default {
  name: 'Home',

  setup() {
    
    const firstname = ref("Issa")
    const lastname = ref("Issifou")
    const age = ref(88)

    const name_and_age = ref({ name : 'Ali', date: 70 })

    let fullname = ref('rrrrr')
    const p = ref(null)

    const add = () => {
      
       fullname.value = firstname.value + ' '  + lastname.value
       p.value.classList.add("test")
    }

    const addDate = () => {
      name_and_age.value.date = 50
    }

     return { firstname, lastname, add, fullname, p, age, name_and_age, addDate }
  },

 
}
</script>

<style scoped>
.test {
  color: red;
  background: greenyellow;
}
</style>
