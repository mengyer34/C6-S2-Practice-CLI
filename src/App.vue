<template>
    <section id="app">
        <friend-nav />
        <friend-form @addFriendCard="addData" />
        <friend-card @deleteFriend="deleteData" v-for="person in people.reverse()" :key="person" :object="person" />
    </section>
</template>
<script>

export default {
    data(){
        return {
            people: [],
        }
    },
    methods: {
        addData(data){
            const person =  {}
            person.id =  new Date().getTime();
            person.firstName = data.firstName;
            person.lastName = data.lastName;
            person.comment = data.comment;
            this.people.push(person);
            
        },
        deleteData(id){
            const index = this.people.findIndex(person => person.id === id);
            this.people.splice(index, 1);
        }
    }
}
</script>
