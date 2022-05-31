<template>
  <div>
       <h2>Admins List</h2>
            <table class="table">
                <thead>
                    <tr>
                        <th scope="col">Name</th>
                        <th scope="col">Age</th>
                        <th scope="col">Email</th>
                    </tr>
                </thead>
                <tbody>
                    <template v-for="admin in adminArray" :key="admin.name">
                        <tr> 
                            <td >{{admin.name}}</td>
                            <td>{{admin.age}}</td>
                            <td>{{admin.email}}</td>
                            <td><button @click="deleteAdminClicked(admin.name)">Delete</button></td>
                        </tr>
                     </template>
                </tbody>
            </table>

            
            
  </div>
</template>

<script>
    export default {
        name:'adminsApp',
        props: ['adminArray'],
        methods:{
            deleteAdminClicked(name){
                console.log(name)
                this.$emit('deleteAdminClicked',name)
            }
        }
        
    }
</script>

<style scoped>

</style>