<template>
<div class="card">
  
  <div class="image">
    <img src="https://picsum.photos/200/200" alt="">
  </div>
  <div class="cont">
    <h1>Lorem, ipsum dolor </h1>
    <p v-if="statement">{{name}} ipsum dolor, sit amet consectetur adipisicing elit. Debitis consectetur quisquam corrupti voluptas nulla officiis ipsum laborum sequi delectus similique nisi, vitae eligendi. Voluptatum natus illo praesentium dicta rem excepturi?</p>
  </div>

  <!-- looping through an array -->
  <div class="looping">
  <ul>
    <li v-for="person in array" :key="person.age">
      {{person.name}} : {{person.age}}
    </li>
  </ul>
</div>

<!-- form -->
  <div class="form">
    <input type="text" v-model="namee">
    <input type="number" v-model="age">
    <button :class="dis"  @click="hello">add to list</button>
    <button @click="me">click</button>
    {{check}}
  </div>

<Edit data="array"/>



</div>

</template>

<script>
import Edit from './Edit';


export default {
  name: 'HelloWorld',
  components:{
    Edit
  },
  props: {
    msg: String

  },
  data:function(){
    return{
      name:'Philani',
      statement:true,
      namee:'',
      age:'',
      check:'',
      
      array:[
        {name:'Philani', age:22},
        {name:'Philile', age:23},
        {name:'Sithembiso', age:24},
        {name:'Nomonde', age:25},
        {name:'Mhayise', age:26},
      ]
    }
  },
  methods:{
    hello:function(){
      this.array.push({name:this.namee,age:this.age});
    },
    me:function(){
      this.check = typeof(this.array);
    }
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style lang="css" scoped>
  .card{
    width: 200px;
    border: 2px solid black;
    border-radius: 30px;
    padding: 20px;

  }
  .image{
    display: flex;
    justify-content: center;
  }
 
</style>
