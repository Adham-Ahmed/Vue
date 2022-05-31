<template>
  <div class="container">
       <form>
            <div >
            <input type="text" placeholder="Name" v-model="name" class="form-control"/>
            </div>
            <div>
                <input type="text" placeholder="Age" v-model="age" class="form-control"/>
            </div>
            <div>
                <input type="text" placeholder="Email" v-model="email" class="form-control"/>
            </div>
            <input type="radio" id="Student" name="type" value="Student" v-model="type">
            <label for="Student">Student</label><br>
            <input type="radio" id="Admin" name="type" value="Admin" v-model="type">
            <label for="Admin">Admin</label>


            <br>
            <button class="btn btn-primary" type="submit" @click.prevent="handleSubmit()" >Add User</button>
       </form>
  </div>
</template>

<script>
    export default {
        name:'formApp',
        data(){
            return {
                'name':"",
                'age':"",
                'email':"",
                'type':'student'
            }

        },
        methods:{
            handleSubmit(){
                // console.log("handle submit"+this.type,)
                // return "bla"
                this.$emit('clickedEvent',[this.name,this.age,this.email,this.type])
            }
        }
    
        
    }
</script>

<style scoped>

</style>