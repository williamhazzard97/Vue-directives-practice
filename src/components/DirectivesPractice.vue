<template>
  <div class="hello">
    <div class="holder">
      <!-- Using v-for to loop through predifined 'skills' array -->
      <div>
        <ul>
          <li v-for="(data, index) in skills" :key= 'index'>
            {{index}}. {{data.skill}}
          </li>
        </ul>
      </div>

      <br>

      <!-- Using v-if="" and v-else directive to test for a condition and produce the correct output to a specific html tag -->
      <div>
        <h2 v-if="skills.length >= 1">You got skills man!</h2>
        <h2 v-else>Time to skill up!</h2>
      </div>

      <br>
      
      <!-- Using v-bind:class to add one or more classes to a specific html tag -->
      <div v-bind:class="{ alert: showAlert, 'anotherClass': anotherClass}">
        V-bind class
      </div>

      <br>

      <!-- Using v-bind:style to add one or more CSS styles directly to a specific html tag -->
      <div v-bind:style="{ backgroundColor: bgColor, width: bgWidth, height: bgHeight, opacity: opacity, color: color, margin: margin}">
        v-bind styles
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: 'DirectivesPractice',
    data() {
      return {
        skills: [
          { "skill": "Vue.js"},
          { "skill": "Frontend Developer"},
          { "skill": "Backend Devloper"},
        ],

        showAlert: true,
        anotherClass: true,


        bgColor: '#000fff',
        bgWidth: '80%',
        bgHeight: '75px',
        opacity: 0.8,
        color: '#ffffff',
        margin: 'auto',
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
</style>
