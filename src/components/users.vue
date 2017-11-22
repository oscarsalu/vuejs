<template>
    <div class="users">
        <div class='grid-x grid-padding-x'>
            <div class='large-3 middle-3 cell'>
            </div>
            <div class='large-6 middle-6 cell'>
                <h1>Users</h1>
                <form v-on:submit = 'addUser'>
                    <input v-model="newUser.name" placeholder="Enter Name" type="text" />
                    <br>
                    <input v-model="newUser.email" placeholder="Enter Email" type="text" />
                    <br>
                    <input type="submit" value="submit">
                </form>
                <ul>
                    <li v-for="user in users">
                        <input v-model="user.contacted" type="checkbox" class="toggle" />
                        <span v-bind:style="styleObject" :class="{contacted: user.contacted}">
                            {{ user.name }} -:- {{user.email}}
                            <button v-on:click="deleteUser(user)">x</button>
                        </span>

                    </li>
                </ul>
            </div>
            <div class='large-3 middle-3 cell'>
            </div>
        </div>
    </div>
</template>
<script>
    export default {
        name: 'users',
        data() {
            return {
                newUser: {},
                styleObject: {
                    color: 'red',
                    fontSize: '13px'
                },
                users: [
                    {
                        name: 'Oscar Salu',
                        email: 'os@asdf.com',
                        contacted: false
                    },
                    {
                        name: 'Name lees',
                        email: 'nl@asdf.com',
                        contacted: false
                    },
                    {
                        name: 'Data Culo',
                        email: 'dc@asdf.com',
                        contacted: false
                    }
                ]
            }
        },
        methods: {
            addUser: function (e) {
                this.users.push({
                    name: this.newUser.name,
                    email: this.newUser.email,
                    contacted: false
                });
                e.preventDefault();
            },
            deleteUser: function (user) {
                this.users.splice(this.users.indexOf(user), 1)
            }
        }
    }
</script>

<style scoped>
    .contacted{
        text-decoration:line-through;
        color: black!important;
    }
    ul{
        list-style-type: none;
    }
</style>
