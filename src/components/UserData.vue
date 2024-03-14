<template>
    <section id="form-section">
        <form @submit.prevent="submitData"> 
            <div>
                <label>Your Name</label>
                <input type="text" v-model="enteredName"/>
            </div>
            <div>
                <label>Your Age</label>
                <input type="text" v-model="enteredAge"/>
            </div>
            <button>Set User Data</button>
        </form>
    </section>
</template>


<script>
export default {
    emits: ['set-data'],
    data() {
        return {
            enteredName: '',
            enteredAge: ''
        }
    },
    methods: {
        submitData() {
            this.$emit('set-data', this.enteredName, this.enteredAge)
        }
    }
}
</script>

