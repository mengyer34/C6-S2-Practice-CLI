<template>
    <form action="#">
        <input class="input-form" v-model="firstName" type="text" placeholder="First Name">
        <input class="input-form" v-model="lastName" type="text" placeholder="Last Name">
        <input class="input-form" v-model="comment" type="text" placeholder="Comment">
        <button class="input-form" @click="addData" :disabled="!validateInput">ADD</button>
    </form>
    <friend-card :methodDelete="deleteData" :object='people'></friend-card>

</template>
<script>
function unquidId(){
    return new Date().getTime();
}
export default {
    data(){
        return {
            people: [],
            firstName: "",
            lastName: "",
            comment: "",
            fullName: "",
        }
    },
    methods: {
        addData(){
            const person =  {id: unquidId(), name: this.fullName, comment: this.comment}
            this.people.push(person);
            this.firstName = ''
            this.lastName = ''
            this.comment = ''
        },
        deleteData(id){
            const index = this.people.findIndex(person => person.id === id);
            this.people.splice(index, 1);
        }
    },
    computed: {
        validateInput(){
            return this.firstName.trim().length > 0 && this.lastName.trim().length > 0 && this.comment.trim().length > 0
        }
    },
    watch: {
        firstName: function (val) {
            this.fullName = val + ' ' + this.lastName
    },
        lastName: function (val) {
            this.fullName = this.firstName + ' ' + val
        }
    }
}
</script>
<style>
form {
    margin: 0 auto;
    width: 70%;
    padding: 10px;
    border-radius: 10px;
    box-shadow: 1px 1px 5px 3px rgba(192, 189, 189, 0.587);
}
form .input-form {
    padding: 10px;
    width: 100%;
    box-sizing: border-box;
    margin: 5px 0;
}
</style>