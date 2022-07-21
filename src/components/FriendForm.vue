<template>
    <form @submit.prevent="setInfo">
        <input class="input-form" v-model="personInfo.firstName" type="text" placeholder="First Name">
        <input class="input-form" v-model="personInfo.lastName" type="text" placeholder="Last Name">
        <input class="input-form" v-model="personInfo.comment" type="text" placeholder="Comment">
        <button class="input-form" :disabled="!validateInput" type="submit">ADD</button>
    </form>
</template>
<script>

export default {
    emits: ["addFriendCard"],
    data(){
        return {
            personInfo: {
                firstName: "",
                lastName: "",
                comment: "",
                fullName: "",
            },
            checkedNames: []
        }
    },
    methods: {
       setInfo(){
        this.$emit('addFriendCard', this.personInfo);
        this.personInfo.firstName = ''
        this.personInfo.lastName = ''
        this.personInfo.comment = ''
       }
    },
    computed: {
        validateInput(){
            return this.personInfo.firstName.trim().length > 0 && this.personInfo.lastName.trim().length > 0 && this.personInfo.comment.trim().length > 0
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