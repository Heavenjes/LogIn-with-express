<template>
<div id="container">
    <div class="jumbotron">
        <h1>Personal Information</h1>
    </div>
    <div id="card">
        <b-card no-body class="overflow-hidden" style="max-width: 540px;">
            <b-row no-gutters>
                <b-col md="6">
                    <b-card-img :src="require('assets/users.png')" class="rounded-0"></b-card-img>
                </b-col>
                <b-col md="6">
                    <b-card-body title="Personal Info">
                        <hr>
                        <b-card-text>
                            <h6>Username: {{username}}</h6>
                            <h6>Email: {{email}}</h6>
                            <h6>Password: {{password}}</h6>
                        </b-card-text>

                    </b-card-body>
                    
                </b-col>
            </b-row>
        </b-card>
        <br>
        <button class="btn btn-primary" id="button2"  @click="update()">Edit Profile</button>

    </div>
</div>
</template>

<style>
.jumbotron {
    padding: 20px;
    text-align: center;
    background-color:pink;
}

#card {
    margin-top: 50px;
    margin-left: 380px;
}

#button2{
    font-size: 20px;
    margin-top: 10px;
    margin-left:12%;
    background: linear-gradient(#22abe9 5%, #36caf0 100%);
    border: 1px solid #0F799E;
    padding: 7px 35px;
    color: white;
    text-shadow: 0px 1px 0px #13506D;
    font-weight: bold;
    border-radius: 2px;
    cursor: pointer;
    width: 20%;
}
h1{
   
}

#button2:hover {
    background: linear-gradient(#36caf0 5%, #22abe9 100%);
}

</style>

<script>
import AUTH from 'services/auth'
export default {
    name: "container",
    data() {
        return {
            username: sessionStorage.getItem("Username"),
            email: sessionStorage.getItem("Email"),
            password: sessionStorage.getItem("Password")
        };
    },
    methods: {
        update: function () {
            AUTH.update(this.username, this.email, this.password)
        }
    }
};
</script>
