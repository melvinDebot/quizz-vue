<template>
  <main>
    <h1>{{ quizz.title }}</h1>
    <div v-for="(question, index) in quizz.question" :key="question.id">
      <div v-show="index === questionIndex">
        <h2>{{ question.text }}</h2>
        <ul>
        <li v-for="response in question.responses" :key="response.id">
          <label>
            <input 
              type ="radio"
              v-bind:value="response.correct" 
              v-bind:name="index" 
            >
            {{ response.text }}
          </label>
        </li>
        </ul>
        <button v-if="questionIndex > 0" v-on:click="prev">
        prev
      </button>
      <button v-on:click="next">
        next
      </button>
      </div>
    </div>
    
  </main>
</template>

<script>
// @ is an alias to /src
// import HelloWorld from '@/components/HelloWorld.vue'
import gsap from 'gsap';
import survey from '../quizz.json';

export default {
  name: 'Home',
  data : function(){
    return {
      quizz : survey,
      questionIndex: 0,
      
    }
  },
  
  methods: {
    next: function() {
      this.questionIndex++;
    },
    prev: function() {
      this.questionIndex--;
    },
    
  }
}
</script>


<style>
main{
  width:100%;
  height:100vh;
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;
}
ul,li{
  list-style: none
}
</style>

