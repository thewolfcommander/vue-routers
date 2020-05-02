<template>
    <nav>
        <ul>
            <li><router-link :to="{ name: 'Home' }">Home</router-link></li>
            <li><router-link :to="{ name: 'About' }">About</router-link></li>
        </ul>

        <h3>User Profile</h3>
        <ul>
            <li v-for="(id, index) in userIds" :key="index">
                <router-link :to="{ name: 'ViewProfile', params: { user_id: id } }">{{ id }}</router-link>
            </li>
        </ul>

        <h3>Navigation Controls</h3>
        <ul>
            <li><button @click="goBack">Go back</button></li>
            <li><button @click="goHome">Redirect to home</button></li>
            <li><button @click="goForward">Go Forward</button></li>
        </ul>
    </nav>
</template>

<script>
export default {
    name: 'Navbar',
    data() {
        return {
            userIds: ['manoj', 'monu', 'simmy', 'simran']
        }
    },
    methods: {
        goHome() {
            this.$router.push({ name: 'Home'})
        },
        goBack() {
            this.$router.go(-1)
        },
        goForward() {
            this.$router.go(1)
        }
    }
}
</script>

<style scoped>
ul {
    list-style-type: none;
}

li {
    display: inline-block;
    margin: 15px;
}

a.router-link-exact-active {
    color: orangered;
    text-decoration: none;
    cursor: pointer;
    font-weight: bolder;
}
</style>