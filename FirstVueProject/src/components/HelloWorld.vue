<script>
import ChildComponent from "./ChildComponent.vue";
export default {
  data() {
    return {
      count:0,
      HTMLValue:'<div style="color:green">Hello World</div>',
      bindValue: "1",
      boolValue: true,
      ObjectValue: {
        id: 1,   
        value: "value Object",
        style:"color:red"
      },
      AttributeValue:"maxlength",
      maxLengthValue:12,
      AttributeTrigger: "click",
      library: [
        {
          author: "toan",
          content:"content book"
        },
        {
          author: "toan",
          content:"content book"
        }
      ],
      Information: {
        firstName: "Le Khanh",
        lastName : "Toan"
      },
      isActive: false,
      classValueObject: {
        'isActive': this.isActive,
        'plain-container': !this.isActive
      }
    } 
  },
  components: {
    ChildComponent
  },
  methods: {
    ReturnTrue(){
      var string = `test1-${this.boolValue}`;
      console.log(string);
      return !this.boolValue;
    },
    ClickEventHandler() {
      this.FullName = "Nguyen YenChi";
      console.log(this.firstName +"??" + this.lastName);
    },
    Increment() {
      this.count++;
    }
  },
  mounted() {
    console.log(this.library);
  },
  //use to write some funcs that will be call in html parts
  computed: {
    IfLibraryEmpty() {
      return this.library.length > 0 ? 'not empty' : 'empty' 
    },
    FullName: {
      get() {
        return this.firstName +" "+ this.lastName;
      },
      set(value) {
          [this.firstName, this.lastName] = value.split(" ");
      }
    },
    classComputedObject() {
      return {
        'isActive': this.isActive,
        'plain-container':!this.isActive
      }
    }
  }
}
</script>
<template>
  <div>{{ boolValue }}</div>
  <input type="text" :id="bindValue" :value="bindValue"/>
  <button @click="()=>{this.boolValue = !this.boolValue}">Change value</button>
  <button :disabled="ReturnTrue()">Show And Hide Value</button>
  <div v-bind="ObjectValue">Test Passing Object Value</div>
  <input type="text" :[AttributeValue]="maxLengthValue + 1" />
  <button @[AttributeTrigger] = "ClickEventHandler" >Click Here Evebt Handler</button>
  <div style="color:blue">{{ IfLibraryEmpty}}</div>
  <div style="display:flex">
    <button @click="()=>{this.isActive = !this.isActive}">Click Changed</button>
    <div :class="{'isActive' : isActive,'plain-container':!isActive }" >Dummy Content</div>
    <div :class="this.classValueObject" >lorem Content</div>
    <div :class="this.classComputedObject" >Lorem, ipsum. Content</div>
  </div>
  <div :class="[{'isActive' : isActive}  ,'array-binding']">Array Binding Class</div>
<div class="container">
  <ChildComponent class="image-pic"></ChildComponent>
</div>
<div class="style-component">
  <div :style="{borderRadius : '50%', backgroundColor: 'red',textAlign:'center'}">Hello World</div>
  <div :style="{'border-radius': maxLengthValue + 'px',backgroundColor: 'green'}">Hello World</div>
  <div :style="['border-radius:12px','background-color:gray']">Hello World</div>
</div>
</template>
<style scoped>

.isActive{
  color:white;
  background-color:red;
  padding:12px;
}
.array-binding{
  font-size:24px;
  color:yellowgreen;
  font-family: Arial, Helvetica, sans-serif;
}
.array-binding-two{
  padding:12px;
  display:block;
  border-radius: 50%;
}
.image-pic{
  width:120px;
  height:120px;
}

.plain-container{
  padding:12px;
  background-color: gray;
}

</style>
