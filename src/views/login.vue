<template>
    <div id="login">
        <h1>Login</h1>
        <input type="text" name="username" v-model="input.username" placeholder="Username" />
        <button type="button" v-on:click="login()">Login</button>
    </div>
</template>

<script>
    export default {
        name: 'Login',
        data() {
            return {
                input: {
                    username: ""
                }
            }
        },
        methods: {
            login() {
                if(this.input.username != "") {
                    if(this.input.username == this.$parent.mockAccount.username) {
                        this.$emit("authenticated", true);
                        this.$router.replace({ name: "secure" });
                    }   else {
                        //console.log("The username is incorrect");
                    }
                } else {
                    //console.log("A username must be present")
                }
            }
        }
    }
</script>

<style scoped>
    #login {
        width: 500px;
        border: 1px solid #CCCCCC;
        background-color: #FFFFFF;
        margin: auto;
        margin-top: 200px;
        padding: 20px;
    }
</style>