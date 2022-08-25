<template>
  <div class="hello">
    <div class="holder">
      <!-- Calling a custom method called 'addSkill' from the component logic and 'preventing' a page reload before the method executes,
      then using v-model to take input from user and put into 'skills' array -->
      <form @submit.prevent="addSkill">
        <input type="text" placeholder="Enter a skill you have.." v-model="skill">
        {{skill}}
      </form>
      
      <!-- Using v-for to loop through predifined 'skills' array -->
      <div>
        <ul>
          <li v-for="(data, index) in skills" :key= 'index'>
            <h2>{{data.skill}}</h2>
          </li>
        </ul>
      </div>

      <br>

      <!-- Using v-if="" and v-else directive to test for a condition and produce the correct output to a specific html tag -->
      <div>
        <h4 v-if="skills.length >= 1">You got skills man!</h4>
        <h4 v-else>Time to skill up!</h4>
        <br>
        <button v-on:click="clearSkills">Clear Skills List</button>
      </div>

      <br>
      
      <!-- Using v-bind:class to add one or more classes to a specific html tag -->
      <div v-bind:class="{ alert: showAlert, 'anotherClass': anotherClass}">
        v-bind class
      </div>

      <br>

      <!-- Using v-bind:style to add one or more CSS styles directly to a specific html tag -->
      <div v-bind:style="{ backgroundColor: bgColor, width: bgWidth, height: bgHeight, opacity: opacity, color: color, margin: margin}">
        v-bind styles
      </div>

      <!-- Using v-on:click to call custom methods on 'click events' with parameters passed to those methods -->
      <button v-on:click="addCounter(1)">Increase</button>
      
      <button v-on:click="subCounter(1)">Decrease</button>
      <br>
      <button v-on:click="addCounter(10)">Increase by 10</button>
      
      <button v-on:click="subCounter(10)">Decrease by 10</button>

      <p>Counter: {{ counter }} </p>
    </div>

    <!-- Using v-on:mousemove to listen for mouse movements 
    and provide x and y coordinates of the mouse position from the browsers event properties-->
    <div id="canvas" v-on:mousemove="updateXY">
      x-axis: {{x}}
      <br>
      y-axis: {{y}}
    </div>
  </div>
</template>

<script>
export default {
  name: 'DirectivesPractice',
    data() {
      
      return {
        skill: '',
        skills: [
          { "skill": "Vue.js"},
          { "skill": "Frontend Developer"},
          { "skill": "Backend Devloper"},
        ],

        showAlert: true,
        anotherClass: true,
        counter: 0,
        x: 0,
        y: 0,

        bgColor: '#000fff',
        bgWidth: '80%',
        bgHeight: '75px',
        opacity: 0.8,
        color: '#ffffff',
        margin: 'auto',
      }
    },
    methods: {
      addSkill() {
        this.skills.push({skill: this.skill});
        this.skill = '';
      },
      clearSkills(){
        this.skills = [];
      },
      addCounter(inc) {
        this.counter += inc;
      },
      subCounter(dec) {
        this.counter -= dec;
      },
      updateXY(event) {
        this.x = event.offsetX;
        this.y = event.offsetY;
      }
    }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
h3 {
  margin: 40px 0 0;
}
ul {
  list-style-type: none;
  padding: 0;
}
li {
  display: inline-block;
  margin: 0 10px;

}
a {
  color: #42b983;
}

/**Create attributes and characteristics of the v-binded classes */
.alert {
  height: 40px;
  width: 80%;
  margin: auto;
  background-color: yellow;
  opacity: 1;
}

.anotherClass {
  border: 3px solid black;
}

#canvas {
  width: 600px;
  padding: 200px 20px;
  text-align: center;
  border: 1px solid #333;
  margin: auto;
}
</style>
