<template>
  <div class="about">
<transition appear  name="fade"

@before-enter="beforenter"
@enter="enter"
@after-enter="afterenter"
@before-leave="beforeleave"
@leave="leave"
@after-leave="afterleave"
>

    <h1 v-if="showTitle">About</h1>

</transition>
    <p>Lorem ipsum dolor sit amet consectetur adipisicing elit. Cum aperiam officia possimus delectus inventore quod quisquam culpa voluptas iusto, quae maiores quo dolorum, corporis laboriosam a dolore consequatur assumenda nam!</p>
    <p>Lorem ipsum dolor sit amet consectetur adipisicing elit. Cum aperiam officia possimus delectus inventore quod quisquam culpa voluptas iusto, quae maiores quo dolorum, corporis laboriosam a dolore consequatur assumenda nam!</p>
    <p>Lorem ipsum dolor sit amet consectetur adipisicing elit. Cum aperiam officia possimus delectus inventore quod quisquam culpa voluptas iusto, quae maiores quo dolorum, corporis laboriosam a dolore consequatur assumenda nam!</p>
  </div>
</template>

<script>
import { ref } from '@vue/reactivity';
import  gsap from 'gsap';


export default {
  setup() {
    const showTitle=ref(true);
const beforenter=(element)=>{
console.log("before enter");
element.style.transform='translateY(-60px)'
element.style.opacity=0

}
const enter=(element,done)=>{
// console.log(" enter");
// element.style.color='green'
gsap.to(element,{
  duration:3,
  y:0,
  opacity:1,
  ease:'bounce.out',
  onComplete:done,
})

}
 const afterenter=()=>{
// setTimeout(()=>showTitle.value=false,1000)

console.log("after enter");

}
//  const beforeleave=()=>{


// console.log("before leave");

// } 
// const leave=()=>{


// console.log("leave");

// }
//  const afterleave=(el)=>{
   

// setTimeout(()=>showTitle.value=true,1000)
// el.style.color='black'

// console.log("after leave");

// }

return{beforenter,enter,showTitle,afterenter}

  }
}
</script>

<style>
/* .fade-enter-from{
opacity: 0;
}
.fade-enter-active{
  transition: all ease 2s;
}
.fade-leave-to{
opacity: 0;
}
.fade-leave-active{
  transition: all ease 2s;
} */


  .about {
    max-width: 600px;
    margin: 20px auto;
  }
</style>