<template>
<div class="row loginPage">
    <div class="col-md-4"></div>
    <div class="col-md-4">
        <div class="container">
            <div class="card">
                <center>
                    <div class="card-header">REGISTER</div>
                </center>
                <div class="card-body">
                    <div class="form-group">
                        <label for="username" class="bmd-label-floating">Username</label>
                        <input v-model="content.username" type="text" class="form-control" id="uname"  placeholder="Enter username.." required />
                    </div>
                    <div class="form-group">
                        <label for="email" class="bmd-label-floating">Email</label>
                        <input v-model="content.email" type="email" class="form-control" id="email1" placeholder="Enter email..."  required/>
                    </div>
                    <div class="form-group">
                        <label for="password" class="bmd-label-floating">Password</label>
                        <input v-model="content.password" type="password" class="form-control" id="loginpass" placeholder="Enter password..." required />
                    </div>
                    <div class="form-group">
                        <label for="cpassword" class="bmd-label-floating"> Confirm Password</label>
                        <input v-model="content.cpassword" type="password" class="form-control" id="logincpass" placeholder="Enter password..." required />
                    </div>
                    <center>
                        <button id="login2" class="btn btn-primary" @click="submit">
                            Register
                        </button>

                        <div class="ui hidden divider"></div>

                        <div class="ui column grid">
                            <div class="center aligned column">
                                <p>
                                    Got an account? <router-link to="/Login">Log In</router-link>
                                </p>
                            </div>
                        </div>

                    </center>
                </div>
            </div>
        </div>
    </div>
</div>
</template>

<style lang="scss" scoped>
// @import"assets/colors.scss";

// #username{
//   color: $primary !important;
// }
// #pass{
//   color: $primary !important;
</style>

<script>
// import ROUTER from "router";
import AUTH from "services/auth";
export default {
    data() {
        return {
            auth: AUTH,
            content: {
                username: "",
                email: "",
                password: "",
                cpassword: ""
            }
        };
    },
    methods: {
        submit: function (e) {
            e.preventDefault();
            sessionStorage.setItem("Username", this.content.username),
                sessionStorage.setItem("Email", this.content.email),
                sessionStorage.setItem("Password", this.content.password),
                AUTH.register(this.content.email, this.content.password);
        }
    }
};
</script>

<style>

.container {
    width: 400px;
    height: 210px;
    margin: 50px auto;
    font-family: 'Droid Serif', serif;
    position: relative;

}

.card-header {
    background-color: black;
    color: white;
    font-size: 30px;
}

input[type=email],
[type=password],
[type=text] {
    width: 97.7%;
    height: 34px;
    padding-left: 5px;
    margin-bottom: 20px;
    margin-top: 8px;
    box-shadow: 0 0 5px #00F5FF;
    border: 2px solid violet;
    color: black;
    font-size: 16px;
}

#login2 {
    font-size: 20px;
    margin-top: 15px;
    background: linear-gradient(#22abe9 5%, #36caf0 100%);
    border: 1px solid #0F799E;
    padding: 7px 35px;
    color: white;
    text-shadow: 0px 1px 0px #13506D;
    font-weight: bold;
    border-radius: 2px;
    cursor: pointer;
    width: 100%;
}

#login2:hover {
    background: linear-gradient(#36caf0 5%, #22abe9 100%);
}

.card-body {
    background-color: aqua;
    color: black;
    font-size: 20px;
}
</style>
