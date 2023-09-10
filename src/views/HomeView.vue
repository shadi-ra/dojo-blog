<template>
  <!-- <div class="home">
  home 
<p ref="p"> My Name is {{name}} and my age is{{ age }} </p>
<button @click="handleClick">click me</button>
<button @click="age++">add one to age</button>
<input type="text" v-model="name">
  </div> -->




  <!-- <div class="home">
    <h1>Home</h1>
    <h2>Refs</h2>
    <p>{{ ninjaOne.name }} - {{ninjaOne.age }}</p>
    <button @click="updateNinjaOne"> Update ninja one </button>
    <h2>Reactive</h2>
    <p>{{ninjaTwo.name}} - {{ninjaTwo.age}}</p>
    <button @click="updateNinjaTwo"> Update ninja two </button>
  </div> -->



<!-- 
  <div class="home">
    <h1>Home</h1>
    <p>{{ name }}</p>
      <input type="text" v-model="search">
      <p>search term - {{ search }}</p>
    <div v-for="name in matchingNames" :key="name">{{ name }}</div>
  </div> -->


<!-- <div class="home">
  <h1>Home</h1>
  <PostList v-if="showPosts" :posts="posts"/>
  <button @click="showPosts = !showPosts">toggle posts</button>
  <button @click="posts.pop()">Delete a post</button>
</div> -->



<div class="home">
    <h1>Home</h1>
    <div v-if="error">{{ error }}</div>
    <div v-if="posts.length">
      <PostList :posts="posts"/>
    </div>
    <div v-else>
       Loading ...
    </div>
   
</div>
</template>

<script>




// import {ref} from 'vue'

// export default {
//   name: 'HomeView',
//    setup(){
//     const p = ref(null)
//     console.log('setup')
//     let name =ref('mario')
//     let age = ref(30)
   
//       const handleClick = () =>{
//         // console.log('you  clicked me')
//         // console.log(p.value.innerHTML)
//         // p.value.classList.add('test')
//         // p.value.textContent = 'hello,ninjas' 
//         name.value='shadi'
     
//       }

//     return {name,age,handleClick,p}
//    }
// }
// import {ref,reactive} from'vue'
// export default{
//   name:'Home',
//   setup(){
//     const ninjaOne = ref({naem:'mario', age:30})
//     const ninjaTwo = reactive({naem:'luigi', age:35})
//     const updateNinjaOne = () => {
//       ninjaOne.value.age = 40
//     }
//    const updateNinjaTwo =()=>{
//     ninjaTwo.age = 50 
//    }

//     return {ninjaOne , updateNinjaOne,ninjaTwo,updateNinjaTwo}
//   }
// }
// import { computed,ref, watch, watchEffect } from 'vue'

// export default{
//   name:'Home',
//   setup(){
//     const search=ref('')
//     const names = ref(['shafi','mehdi','ali','mina'])
//     watch(search,() => console.log('watch function run'))
//      const matchingNames = computed(()=>{
//       return names.value.filter((name) => name.includes(search.value))
//      })
//      watchEffect(()=>console.log('hello'),search)
//     return{names,search,matchingNames}
//   }
// }



// import PostList from '../components/PostList.vue'
// import {ref} from 'vue'

// export default{
//   name:'Home',
//   components:{PostList},
//   setup(){
//     const posts = ref([
//       {title: 'welcome to the blog' ,body:'Lorem ipsum, dolor sit amet consectetur adipisicing elit. Commodi eius architecto quas dignissimos, sapiente eaque facere quis ut corporis, repellendus culpa cupiditate exercitationem nulla. Quos sapiente fugiat illo animi doloremque repudiandae ad culpa. Qui necessitatibus voluptatibus illum nemo. Eveniet, officia dolorum cupiditate reiciendis asperiores quo quis? Aspernatur aut est cumque aperiam commodi tenetur incidunt, nostrum, quis, ex porro dolor? Nihil eius praesentium modi dignissimos, voluptatibus unde? Similique laborum, dicta dolor enim adipisci, modi accusamus quam sed consequuntur est nihil odit totam velit et nulla blanditiis voluptates eligendi culpa in! Sed tempore excepturi exercitationem molestias doloremque, quam nobis vero nihil, illum ipsam consequatur adipisci. Esse natus blanditiis impedit odio minus sit at asperiores, commodi totam inventore omnis consequuntur tempora ipsa. Facilis.' ,id:1},
//       {title: 'top 5 css tips',body: 'Lorem ipsum, dolor sit amet consectetur adipisicing elit. Commodi eius architecto quas dignissimos, sapiente eaque facere quis ut corporis, repellendus culpa cupiditate exercitationem nulla. Quos sapiente fugiat illo animi doloremque repudiandae ad culpa. Qui necessitatibus voluptatibus illum nemo. Eveniet, officia dolorum cupiditate reiciendis asperiores quo quis? Aspernatur aut est cumque aperiam commodi tenetur incidunt, nostrum, quis, ex porro dolor? Nihil eius praesentium modi dignissimos, voluptatibus unde? Similique laborum, dicta dolor enim adipisci, modi accusamus quam sed consequuntur est nihil odit totam velit et nulla blanditiis voluptates eligendi culpa in! Sed tempore excepturi exercitationem molestias doloremque, quam nobis vero nihil, illum ipsam consequatur adipisci. Esse natus blanditiis impedit odio minus sit at asperiores, commodi totam inventore omnis consequuntur tempora ipsa. Facilis.' , id:2},
//     ])
//    const showPosts = ref(true)

//     return {posts, showPosts}
//   }
// }




import PostList from '../components/PostList.vue'
import getPosts from '../composables/getPosts'

export default{
  name:'Home',
  components:{PostList},
  setup(){
    const {posts, error, load } = getPosts()

    load()

    return {posts,error}
  }
}
</script>  

