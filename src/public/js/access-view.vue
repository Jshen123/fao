<template>
    <div id="access">
        <div class="flex-center">
            <h1 class='title'>Please enter the access code</h1>
        </div>
        <div class="flex-center">    
            <input type="text" class="password-input" name="password" @change="handleInput" @input="handleInput" placeholder="Password" />
        </div>
        <div class="flex-center">
            <button type="button" id="access-button" class="btn big primary" v-on:click="access()">Access</button>
        </div>
    </div>
</template>

<script>
import Store from './state';
import VIEW from './view';
    export default {
        name: 'Access',
        data() {
            return {
                input: {
                    password: ""
                }
            }
        },
        methods: {
            handleInput({target}){
                this.input.password = target.value
            },
            access() {
                if(this.input.password != "") {
                    if(this.input.password == Store.state.password) {
                        this.$emit("authenticated", true);
                        // this.$router.replace({ name: "secure" });
                        localStorage.password = this.input.password;
                        Store.setView(VIEW.HOME)
                    } else {
                        console.log("The password is incorrect");
                    }
                } else {
                    console.log("A password must be present");
                }
            }
        },
        beforeMount(){
            Store.submitPassword();
        }
    }
</script>

<style scoped>
    #access {
        width: 500px;
        border: 1px solid #CCCCCC;
        background-color: #FFFFFF;
        margin: auto;
        margin-top: 200px;
        padding: 20px;
    }