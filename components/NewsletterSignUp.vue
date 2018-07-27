<template>
    <div class="newsletterSignUpContainer">

        <span class="successMessage" v-if="formSuccessful">{{successMessage}}</span>

        <form id="app" @submit="checkForm" method="post" v-if="!formSuccessful">

            <div v-if="errors.length">
                <b>Please correct the following error(s):</b>
            </div>

            <div class="inputField">
                <label for="name">Name <span class="optional">(optional)</span></label>
                <input type="text" name="name" id="name" v-model="name">
            </div>

            <div class="inputField">
                <label for="email">Email</label>
                <input type="email" name="email" id="email" v-model="email">
                <span class="errorMessage">{{errors.email}}</span>
            </div>

            <div class="inputField">
                <label for="message">Message</label>
                <textarea name="message" id="message" v-model="message"></textarea>
                <span class="errorMessage">{{errors.message}}</span>
            </div>

            <div class="">
                <input type="submit" value="Submit">
            </div>

        </form>
    </div>
</template>

<script>
export default {
    data: function() {
        return {
            errors: {},
            name: null,
            email: null,
            message: null,
            successMessage: "Message submitted.",
            formSuccessful: false
        }
    },
    methods: {
        checkForm: function(e) {
            e.preventDefault();
            if (this.email && this.message) {
                this.name = "";
                this.email = "";
                this.message = "";
                this.errors = {};
                this.formSuccessful = true;
                return true;
            }else {
                this.errors = {};
            }
            
            if (!this.email) {
                this.errors['email'] = "Email required.";
            }
            if (!this.message) {
                this.errors['message'] = "Message required.";
            }
        }
    }
}
</script>


<style>

.newsletterSignUpContainer {
    width: 250px;
    margin: auto;
}

.optional {
    font-style: italic;
}

.successMessage {
    color: green;
}

.errorMessage {
    color: red;
}

.inputField {
    margin-bottom: 20px;
}

input, textarea {
    background: transparent;
    border: 1px solid gray;
    width: 100%;
}

textarea {
    min-height: 50px;
    max-width: 98%;
    min-width: 98%;
}

input[type="submit"] {
    width: 50%;
}

</style>
