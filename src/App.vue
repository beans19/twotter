<template>
<div id="app">
    <!-- dinamic data point -->
    @{{user.username}} - {{fullName}}
    <strong>Followers: </strong> {{followers}}
    <button @click="followUser">Follow</button>
</div>
</template>

<script>
export default {
    name: "App",
    data() {
        //data works as a function and we return the data that we want
        return {
            followers: 0,
            user: {
                id: 1,
                username: 'beans19',
                firstName: 'Felipe',
                lastName: 'Stefani',
                email: 'felipemarqs2015@gmail.com',
                isAdmin: true
            }
        };
    },
    //computed data
    computed: {
        fullName() {
            return `${this.user.firstName} ${this.user.lastName}`;
        }
    },
    methods: {
        followUser() {
            this.followers++
        }
    },
    mounted() {
        this.followUser();
    }
};
</script>

<style>
#app {
    font-family: Avenir, Helvetica, Arial, sans-serif;
    -webkit-font-smoothing: antialiased;
    -moz-osx-font-smoothing: grayscale;
    color: #2c3e50;
    display: flex;
    flex-direction: column;
    text-align: center;
}
</style>
