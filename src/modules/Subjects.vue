<template>
<div>
    <div class="jumbotron">
        <h1>Subjects</h1>
    </div>
    <center>
        <b-card text-align id="card" img-top tag="article" style="max-width: 30rem;" class="mb-2">
            <b-form-group label-size="lg" label-for="input-lg">
                <label id="Subject">Subject:</label>
                <b-form-input v-model="infos.subject" id="subject" type="text" size="lg"></b-form-input>
                <label id="teacher">Teacher:</label>
                <br>
                <b-form-input v-model="infos.teacher" id="teacher" type="text" size="lg"></b-form-input>
                <br>
                <label id="time">Time:</label>
                <b-form-input v-model="infos.time" id="time" type="text" size="lg"></b-form-input>
                <label id="time">Day:</label>
                <b-form-input v-model="infos.day" id="day" type="text" size="lg"></b-form-input>
                <label id="room">Room:</label>
                <b-form-input v-model="infos.room" id="room" type="text" size="lg"></b-form-input>
                <br>
                <b-button variant="primary" @click="addItem">Add Subject</b-button><br><br>
                <b-button variant="primary" @click="removeItem">Remove</b-button>
            </b-form-group>
        </b-card>
        <b-card text-align id="card1" img-top tag="article" style="max-width: 40rem;" class="mb-2">
            <table class="table">
                <thead>
                    <tr>
                        <th scope="col">SUBJECT</th>
                        <th scope="col">TEACHER</th>
                        <th scope="col">TIME</th>
                        <th scope="col">DAY</th>
                        <th scope="col">ROOM</th>
                    </tr>
                </thead>
                <tbody v-for="(item, index) in this.rows" :key="index">
                    <tr>
                        <td>{{ item.subject }}</td>
                        <td>{{ item.teacher }}</td>
                        <td>{{ item.time }}</td>
                        <td>{{ item.day }}</td>
                        <td>{{ item.room }}</td>

                    </tr>
                </tbody>
            </table>
        </b-card>
    </center>
</div>
</template>

<style>
#card {
    margin-top: 10px;
    height: 0%;
    margin-right:30%;
}

.jumbotron {
    padding: 2%;
    text-align: center;
    background-color:brown;
    color:white;
}

#card1{
    border-collapse: collapse;
    border-spacing: 0;
    width:500px;
    height: 200px;
    border: 1px solid aqua;
    overflow:scroll;
    margin-bottom: -30%;
    margin-right:3%;

}

input[type="text"] {
  width: 97.7%;
  height: 34px;
  padding-left: 5px;
  margin-bottom: 20px;
  margin-top: 8px;
  box-shadow: 0 0 5px #00f5ff;
  border: 2px solid violet;
  color: black;
  font-size: 16px;
}



</style>

<script>
export default {
    data() {
        return {
            rows: [],
            infos: {
                subject: "",
                teacher: "",
                time: "",
                day: "",
                room: "",
            }
        }
    },
    methods: {
        addItem() {
            var object = {
                subject: this.infos.subject,
                teacher: this.infos.teacher,
                time: this.infos.time,
                day: this.infos.day,
                room: this.infos.room
            };
            this.rows.push(object)
            this.infos.subject = ""
            this.infos.teacher = ""
            this.infos.time = ""
            this.infos.day = ""
            this.infos.room = ""
        },

        removeItem() {
            var object = {
                subject: this.infos.subject,
                teacher: this.infos.teacher,
                time: this.infos.time,
                day: this.infos.day,
                room: this.infos.room
            };
            this.rows.splice(object, 1)

        }

    }
}
</script>
