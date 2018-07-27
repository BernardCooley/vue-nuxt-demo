<template>
    <div class="navigationContainer">
        <ul>
            <router-link tag="li" to="/home">
                <span>Home</span>
            </router-link>
            <router-link tag="li" to="/music">
                <span>Music</span>
            </router-link>
            <router-link tag="li" to="/videos">
                <span>Videos</span>
            </router-link>
            <router-link tag="li" to="/contact">
                <span>Contact</span>
            </router-link>
            <router-link tag="li" to="/bio">
                <span>Bio</span>
            </router-link>
        </ul>
    </div>
</template>

<script>

</script>


<style scoped>

.navigationContainer {
    font-size: 2em;
    display: flex;
    flex-direction: column;
    justify-content: center;
    align-items: center;
    text-align: center;
    padding-bottom: 50px;
    }

ul {
    list-style: none;
    display: flex;
}

li {
    text-align: center;
    padding: 0.2em 0.5em 0.2em 0.5em;
}

span {
    text-decoration: none;
    color: darkgray;
    -moz-user-select: none;
    -khtml-user-select: none;
    -webkit-user-select: none;
    -ms-user-select: none;
    user-select: none;
}

span:hover {
    color: black;
    cursor: pointer;
}

span:visited {
    color: none;
}

.nuxt-link-active {
    border-bottom: 0.1em solid black
}

.nuxt-link-active span {
    color: black;
}
</style>
