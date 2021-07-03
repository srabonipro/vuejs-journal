<template>
    <div>

        <h1>Hello, {{ username }} </h1>
        <router-link :to="{name: 'invoices'}">
            <button class="btn">Invoices</button>
        </router-link>

        <br> <br>
        
        <button class="btn" @click="logout">Logout</button>

        
    </div>
</template>

<script>
export default {
    data() {
        return {
            username: window.user
        }
    },
    methods: {
        logout() {
            window.user = null
            this.$router.push({name: 'Home'})
        }
    }
}
</script>