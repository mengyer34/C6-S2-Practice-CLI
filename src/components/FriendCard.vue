<template>
<section>
    <div class="card">
        <h1>{{object.firstName}} {{object.lastName}}</h1>
        <p>{{object.comment}}</p>
        <button @click="clickDelete()">Delete</button>
    </div>
</section>
</template>
<script>
    export default {
        emits: ['deleteFriend'],
        props: {
            object: Object,
        },
        methods: {
            clickDelete(){
                this.$emit('deleteFriend', this.object.id);
            }
        }
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