<template>
  <div>
    <div class="jumbotron">
      <h1>Dashboard</h1>
    </div>
    <div id="card">
      <b-card no-body class="overflow-hidden" style="max-width: 540px;">
        <center>
          <b-card-img id="image" :src="require('assets/users.png')" class="rounded-0"></b-card-img>
          <b-row no-gutters>
            <b-card-body>
              <h2>Hi {{username}}</h2>
              <h3>WELCOME TO DASHBOARD</h3>
            </b-card-body>
          </b-row>
        </center>
      </b-card>
    </div>
  </div>
</template>

<style scoped>
#card {
  margin-top: 3%;
  margin-left: 28%;
  color: aqua;
}

.jumbotron{
    padding:2%;
    text-align: center;
    background-color:brown;
    color:white;
}
#image {
  width: 40%;
  height: 30%;
}
</style>

<script>
// import ROUTER from "router";
export default {
  name: "card",
  data() {
    return {
      username: sessionStorage.getItem("Username")
    };
  },
};
</script>

