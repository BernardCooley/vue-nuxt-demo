<template>
    <div class="newsletterSignUpContainer">
        <form id="app" @submit="checkForm" action="/home" method="post">

            <p v-if="errors.length">
                <b>Please correct the following error(s):</b>
            </p>

            <p>
                <label for="name">Name</label>
                        <input type="text" name="name" id="name" v-model="name">
            </p>

            <p>
                <label for="age">Age</label>
                        <input type="number" name="age" id="age" v-model="age">
            </p>

            <p>
                <label for="movie">Favorite Movie</label>
                        <select name="movie" id="movie" v-model="movie">
                            <option>Star Wars</option>
                            <option>Vanilla Sky</option>
                            <option>Atomic Blonde</option>
                        </select>
            </p>

            <p>
                <input type="submit" value="Submit">
            </p>

        </form>
    </div>
</template>

<script>
export default {
    data: function() {
        return {
            errors: [],
            name: null,
            age: null,
            movie: null
        }
    },
    methods: {
        checkForm: function(e) {
            if (this.name && this.age) return true;
            this.errors = [];
            if (!this.name) this.errors.push("Name required.");
            if (!this.age) this.errors.push("Age required.");
            e.preventDefault();
            submitForm(e);
        },
        submitForm: function(e) {
            console.log('Form submitted');
            e.preventDefault();
        }
    }
}
</script>


<style>

</style>
