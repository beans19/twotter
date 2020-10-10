<template>
<div id="app">
    <div class="user-profile">
        <div class="user-profile__user-panel">
            <h1 class="user-profile__username">@{{user.username}}</h1>
            <div class="user-profile__follower-count">
                <strong>Followers: </strong> {{followers}}
            </div>
        </div>
    </div>
</div>
</template>

<script>
export default {
    name: 'UserProfile',
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
    //watch for data
    watch: {
        //watches for follows, picks the new data and the old one to compare them
        followers(newFollowerCount, oldFollowerCount) {
            (oldFollowerCount < newFollowerCount) ? console.log(`${this.user.username} has gained a follower!`): ""
        }
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

<!-- Add "scoped" attribute to limit CSS to this component only -->

<style>
.user-profile {
    display: grid;
    grid-template-columns: 1fr 3fr;
    width: 100%;
    padding: 50px 5%;
}

.user-profile__user-panel {
    display: flex;
    flex-direction: column;
    margin-right: 50px;
    padding: 20px;
    background-color: white;
    border-radius: 5px;
    border: 1px solid #DFE3E8;
}

h1 {
    margin: 0;
}
</style>
