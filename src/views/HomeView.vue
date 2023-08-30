<template>
  <div class="home">
  home 
<p ref="p"> My Name is {{name}} and my age is{{ age }} </p>
<button @click="handleClick">click me</button>
  </div>
</template>

<script>
import {ref} from 'vue'

export default {
  name: 'HomeView',
   setup(){
    const p = ref(null)
    console.log('setup')
    let name ='mario'
    let age = 30
   
      const handleClick = () =>{
        console.log('you clicked me')
        console.log(p.value.innerHTML)
        p.value.classList.add('test')
        p.value.textContent = 'hello,ninjas' 
      }

    return {name,age,handleClick,p}
   }
}
</script>  

