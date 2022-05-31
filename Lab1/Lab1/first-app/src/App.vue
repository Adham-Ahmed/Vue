<template>
<div>
  <div>
    <button class="btn-info btn m-2" @click="selector=0">Forms</button>
    <button class="btn-info btn m-2" @click="selector=1">Students</button>
    <button class="btn-info btn m-2" @click="selector=2">Admins</button>
  </div>
  <div v-if="selector==0">
  <form-app @clickedEvent="onFormClicked"></form-app>
  </div>

  <div v-if="selector==1">
  <studentsApp :studArray=students @deleteStudentClicked="onStudentDeleteClicked"></studentsApp>
  </div>

  <div v-if="selector==2">
  <adminsApp :adminArray=admins @deleteAdminClicked="onAdminDeleteClicked"></adminsApp>
  </div>
</div>
</template>

<script>

  import  formApp  from "./components/formApp.vue"
  import  adminsApp  from "./components/adminsApp.vue"
  import  studentsApp  from "./components/studentsApp.vue"
export default {
  name: 'App',
  components: {
    formApp,
    adminsApp,
    studentsApp
  },
  data(){
    return {
      selector:0,
      students:[],
      admins:[],
    }
  },
  methods: {
    onFormClicked(value){
      var obj={
        name: value[0],
        age: value[1],
        email: value[2],
        type: value[3],
      }
      if(value[3]=='Student'){
        this.students.push(obj)
      }else{
        this.admins.push(obj)
      }
      console.log(this.students)
    },
    onAdminDeleteClicked(value){
      var index=this.admins.indexOf(value)
      this.admins.pop(index)
    },
     onStudentDeleteClicked(value){
       console.log("from app"+value)
      var index=this.admins.indexOf(value)
      this.students.pop(index)
    }
  }
}
  import 'bootstrap/dist/css/bootstrap.min.css'
  import 'jquery/src/jquery.js'
  import 'bootstrap/dist/js/bootstrap.min.js'
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
 
}
</style>
