<template>
  <div class="container">
    <button class="btn btn-light" @click="EventHandler('Hello From Parameter',$event)"> Click Me
    </button>
  </div>
  <div>{{ valueTest }}</div>
  <div>
    <input type="text" v-model="this.firstName">
    {{ this.firstName }}
  </div>
  <div>
    <input type="text" :value="firstName" @input="(ChangeValue($event))"/>
  </div>
  <div class="card">
    <input name="value" type="checkbox" :value="inputList" /> Value 1
    <input name="value" type="checkbox" :value="inputList" /> Value 2
    <div> {{inputList}}</div>
  </div>

</template>

<script>
export default {
  name: 'EventListenerComponent',
  data() {
    return {
      valueTest:"12",
      firstName: "",
      inputList:[]
    }
  },
  methods:{
    EventHandler(value,event){
      alert(value);
      console.log(event);
    },
    ChangeValue(value) {
      // console.log(value.data);
      // if (value.data == null || value.data == "") {
      //   this.firstName = "";
      //   return;
      // }
      // this.firstName += value.data
      this.firstName = value.target.value;
    }
  }
}
</script>
<style lang="scss" scoped>

</style>