<template>
  <div class="training">
    <h1>Math trainig</h1>
    <hr>
    <app-start-screen 
      v-if = "state == 'start'" 
      @onStart = "onStart">
      
    </app-start-screen>
    <app-result-screen v-else-if = "state == 'results'"></app-result-screen>
    <app-question v-else-if = "state == 'question'"></app-question>
    <app-message v-else-if = "state == 'message'"></app-message>
    <div v-else>Unknow state</div>
  </div>
</template>

<script>
export default {
  name: 'app',
  data () {
    return {
      state: 'start'
    }
  },
  methods: {
    onStart(){
      this.state = 'question';
    }
  }
}
</script>

<style scoped>
  .training {
    max-width: 700px;
    margin: 20px auto;
  }
</style>
