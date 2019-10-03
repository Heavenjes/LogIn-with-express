<template>
<div class="row loginPage">
    <div class="col-md-4"></div>
    <div class="col-md-4">
        <div class="container">
            <div class="card">
                <center>
                    <div class="card-header">LOGIN</div>
                </center>
                <div class="card-body">
                    <div class="form-group">
                        <label for="email" class="bmd-label-floating">Email</label>
                        <input v-model="email" type="email" class="form-control" id="email" placeholder="Enter email address..." />
                    </div>
                    <div class="form-group">
                        <label for="pwd" class="bmd-label-floating">Password</label>
                        <input v-model="password" type="password" class="form-control" id="loginPassword" placeholder="Enter password..." />
                    </div>
                    <center>
                        <button id="login1" class="btn btn-primary"  @click="submit">  <!--@click='submit'-->
                            Login
                        </button>
                        <div class="ui hidden divider"></div>

                        <div class="ui column grid">
                            <div class="center aligned column">
                                <p>
                                    Don't have an account? <router-link to="/Register">Sign Up</router-link>
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
@import "assets/colors.scss";

#username {
    color: $primary !important;
}

#pass {
    color: $primary !important;
}
</style>

<script>
import AUTH from 'services/auth';
// import jquery from 'jquery'
import ROUTER from 'router'
export default {
    data() {
        AUTH
        return {
            email: "",
            password: ""
        };
    },
    methods: {
        submit: function (e) {
            e.preventDefault();
            let user = AUTH.login(this.email, this.password);
            if(this.email == "" || this.password ==""){
                alert("Please Enter your email and password!!!" );
            
            }else{
                alert("Successfully Login ..")
                ROUTER.push('/Register')
                AUTH.setUser(user);
                if(user!=null){
                    ROUTER.push('/Dashboard');
                }
            }
        }
        }

    //     test(){
    //         alert('hi')
    //        let link = 'http://localhost:3000/user'
    //        jquery.ajax({
    //            url:link,
    //            method: 'POST',
    //            headers: {
    //                'Access-control-Allow-Origin': '*'
    //            }
    //        })
           
    //     }
    // },
    // computed:{

    // }

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

#login1 {
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

#login1:hover {
    background: linear-gradient(#36caf0 5%, #22abe9 100%);
}

.card-body {
    background-color: aqua;
    color: black;
    font-size: 20px;
}
</style>
