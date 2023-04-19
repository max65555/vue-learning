<script>
export default {
  data() {
    return {
    } 
  },
  methods: {
    ReturnTrue(){
      var string = `test1-${this.boolValue}`;
      console.log(string);
      return !this.boolValue;
    },
  },
  mounted() {
    console.log(this.count);
    this.count = 2;
  }
}
</script>
<template>
  <div class="container">
    <!-- <input type="text" v-bind:value=""></input> -->
  </div>
</template>
<style scoped>
.container{
  
}
</style>
