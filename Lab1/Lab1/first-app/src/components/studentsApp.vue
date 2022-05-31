<template>
  <div>
       <h2>students List</h2>
            <table class="table">
                <thead>
                    <tr>
                        <th>Name</th>
                        <th>Age</th>
                        <th>Email</th>
                    </tr>
                </thead>
                <tbody>
                    <template v-for="student in studArray" :key="student.name">
                        <tr>
                            <td scope="row">{{student.name}}</td>
                            <td>{{student.age}}</td>
                            <td>{{student.email}}</td>
                            <td><button @click="deleteStudentClicked(student.name)">Delete</button></td>
                        </tr>
                     </template>
                </tbody>
            </table>
            
  </div>
</template>

<script>
    export default {
        name:'studentsApp',
        // data(){
        //     // return {
        //     //     'students':
        //     // }
        // },
        props: ['studArray'],
        methods:{
            deleteStudentClicked(name){
                console.log(name)
                this.$emit('deleteStudentClicked',name)
            }
        }
        
    }
</script>

<style scoped>

</style>