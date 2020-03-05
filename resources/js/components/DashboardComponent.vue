<template>
    <div class="container">
        <div class="row">
            <div class="col-md-8 col-md-offset-2">
                <h1>Dashboard</h1>

                <p>
                    <router-link :to="{ name: 'logout' }">Logout</router-link>
                </p>

                <div class="panel panel-default">
                    <div class="panel-heading">Dashboard</div>
                    <div class="row">
                        <div class="col-6">
                            <p>Send request with JWT token:</p>
                            <button @click="withToken()" class="btn btn-success">Test</button>
                        </div>
                        <div class="col-6">
                            <p>Send request without JWT token:</p>
                            <button @click="withoutToken()" class="btn btn-danger">Test</button>
                        </div>
                    </div>
                </div>

            </div>
        </div>
    </div>
</template>

<script>
    export default {
        methods: {
            withToken() {
                axios.get('/api/dashboard', {
                    headers: {
                        Authorization: 'Bearer ' + localStorage.getItem('token')
                    }
                })
                    .then(response => {
                        alert("Success:" + response.data.data)
                    }).catch(error => {

                })
            },
            withoutToken() {
                axios.get('/api/dashboard', {
                    headers: {
                        // Authorization: 'Bearer ' + localStorage.getItem('token')
                    }
                })
                    .then(response => {

                    }).catch(error => {
                        alert("Error: Check console!");
                        console.log(error.response);
                    })
            }
        }
    }
</script>

<style scoped>

</style>
