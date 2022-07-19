<template>
<section>
    <div class="card" v-for="person in object" :key="person">
        <h1>{{person.name}}</h1>
        <p>{{person.comment}}</p>
    </div>
</section>
</template>
<script>
    export default {
        props: {
            object: Object
        },
    }
</script>
<style>
section {
    margin: 20px 0;
}
.card {
    margin: 20px auto;
    width: 70%;
    padding: 10px;
    border-radius: 10px;
    box-shadow: 1px 1px 5px 3px rgba(192, 189, 189, 0.587);
}
</style>