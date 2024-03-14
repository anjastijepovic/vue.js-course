<template>
    <div>
        <active-user :username="user.name" :userage="user.age"></active-user>
        <user-data @set-data="setUserData"></user-data>
    </div>
</template>


<script>
export default {
    data() {
        return {
            user: {
                name: 'Anja Stijepovic',
                age: '23'
            }
        }
    },
    methods: {
        setUserData(receivedName, receivedAge) {
            this.user = {
                name: receivedName,
                age: +receivedAge
                // the + converts it into number
            };
        }
    }
}
</script>


<style>
/* this will style all sections in the app, not just the component */
/* we can lock styles as well, we will see later */
    html {
        font-family: sans-serif;
    }
    #app section {
        margin: 2rem auto;
        /* centered */
        max-width: 40rem;
        border-radius: 12px;
        border: 1px solid #ccc;
        padding: 1rem;
    }
    #form-section {
        display: flex;
        flex-direction: column;
    }
    #app label {
        font-weight: bold;
        margin-right: 1rem;
        width: 7rem;
        display: inline-block;
    }
    #app input { 
        margin-top: 1rem;
    }
    #app button {
        margin-top: 1rem;
    }
</style>