<template>
    <form action="#">
        <input class="input-form" v-model="firstName" type="text" placeholder="First Name">
        <input class="input-form" v-model="lastName" type="text" placeholder="Last Name">
        <input class="input-form" type="text" v-model="comments" placeholder="Comment">
        <button class="input-form">ADD</button>
    </form>
</template>
<script>

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