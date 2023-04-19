<template>
  <!-- <div>{{this.counter}}</div>
  <div v-show=isTrue>
    <div>
      [if] context  
    </div>
    <img width="120" height="120" src="./racket.jpg" />
  </div> -->
<!-- <div v-else-if="this.counter%3==0">[else if] context</div>
  <div v-else> [else] context </div> -->
  <!-- <div>
    <button class="btn btn-success fixed-button" @click="()=>{this.isTrue = !this.isTrue; this.counter++}" >Click Me</button>
  </div> -->
  <div class="container">
    <div v-for="name in items">
      {{ i }}- {{ iter }}
    </div>
    <div v-for="({name},i) in items">
      {{ name }} - {{ i }}
    </div>
    <div v-for="row in matrix">
      <span v-for="item in row" :style="{padding:'12px'}" class="button-item">
        {{ item }}
      </span>
    </div>
    <div v-for="(value,key,iter) of Person">
      <div class="btn btn-light" :style="{width:'100%',textAlign:'left'}">
        {{key}} : {{ value }}
      </div>
    </div>
    <div v-for="i in 10">
      {{ i }}
    </div>
  </div>
</template>

<script>
  export default {
    data(){
      return {
        isTrue: false,
        counter: 0,
        items: ["Le Khanh Toan", "Le Xuan Do", "Chu Thi Ngan"],
        matrix: [[1, 2, 3], [4, 5, 6], [7, 8, 9]],
        Person: {
          name: "Le Khanh Toan",
          age: 12,
          address: "Viet Nam"
        }
      }
    },
    name: "FounDationComponent",
}
</script>

<style lang="scss" scoped>
div{
  .fixed-button{
    position:fixed ;
    left: 50%;
    bottom: 50%;
  }
}
.button-item:hover{
  background-color:gray;
}
</style> 