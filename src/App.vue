<template>
	<div id="app">
            <table class="table">
                <thead class="thead-dark">
                    <tr>
                        <th scope="col">Id</th>
                        <th scope="col">Name</th>
                        <th scope="col">Username</th>
                        <th scope="col">Email</th>
                        <th scope="col">address.street</th>
                        <th scope="col">address.suite</th>
                        <th scope="col">address.city</th>
                        <th scope="col">address.zipcode</th>
                        <th scope="col">address.geo.lat</th>
                        <th scope="col">address.geo.lng</th>
                        <th scope="col">phone</th>
                        <th scope="col">website</th>
                        <th scope="col">company.name</th>
                        <th scope="col">company.catchPhrase</th>
                        <th scope="col">company.bs</th>
                    </tr>
                </thead>
                <tr scope="row"  :key="user" v-for="user in userList">
                    <td>{{user.id}}</td>
                    <td>{{user.name}}</td>
                    <td>{{user.username}}</td>
                    <td>{{user.email}}</td>
                    <td>{{user.address.street}}</td>
                    <td>{{user.address.suite}}</td>
                    <td>{{user.address.city}}</td>
                    <td>{{user.address.zipcode}}</td>
                    <td>{{user.address.geo.lat}}</td>
                    <td>{{user.address.geo.lng}}</td>
                    <td>{{user.phone}}</td>
                    <td>{{user.website}}</td>
                    <td>{{user.company.name}}</td>
                    <td>{{user.company.catchPhrase}}</td>
                    <td>{{user.company.bs}}</td>
                </tr>
            </table>           
        </div>
</template>

<script>
    import Vue from "vue";

    export default{
        data(){
            return{
               userList: []
            }
        },
        created() 
        {
			    //   Vue.http.get('http://localhost:2225/allusers')
				//     .then(response => {
                //     this.userList = response.data;				
                // });
                
                   Vue.http.get('https://jsonplaceholder.typicode.com/users')
				    .then(response => {
                    this.userList = response.data;				
				});
		}
    }
</script>
