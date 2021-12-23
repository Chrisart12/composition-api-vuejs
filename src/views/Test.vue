<template>
  <div class="test">
        <h1>TEST</h1>
        <p v-for="name in matchingNames" :key="name">{{ name }} </p>
        <p>
            <input type="text" v-model="search">
        </p>
        <p> {{ search }} </p>
  </div>
</template>

<script>
import { computed , ref, watch, watchEffect } from "vue";
export default {
    setup() {
        const search = ref('')
        const names = ref(["Toto", "Tata", "Titi", "Toutou", "Tutu", "Tete"])

          watch(search, () => {
            console.log('Watch function run')
        })

        const matchingNames = computed(() => {
            // return names.value.filter(name => name.toLowerCase().indexOf(search.value.toLowerCase()) !== -1 )
            return names.value.filter(name => name.toLowerCase().includes(search.value.toLowerCase()))
        })

        watchEffect(() => {
            console.log('watchEffect function ran')
        })
            

        return { names, search, matchingNames }
    }
}
</script>

<style>

</style>