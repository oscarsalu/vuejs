<template>
    <div class="test">
        <h1>{{title}}</h1>
        <p>{{user.firstName}}</p>
        <p v-text="user.lastName"></p>
        <label for="firstName">First Name: </label>
        <input type="text" v-model="user.firstName">
        <br>
        <label for="lastName">Lase Name: </label>
        <input type="text" v-model="user.lastName">
        <h3>{{fullName}}</h3>
    </div>
</template>
<script>
    export default {
        name: 'test',
        data() {
            return {
                title: 'Vue App' ,
                user: {
                    firstName: 'Name',
                    lastName: 'less'
                }
            }
        },
        computed: {
            fullName: function () {
                return this.user.firstName+' '+this.user.lastName;
            }
        }
    }
</script>

<style scoped>

</style>
