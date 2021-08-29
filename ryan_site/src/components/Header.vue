<template>
    <div class="header_frame">
        <h1>Ryan Lambert</h1>
        <div class="nav">
            <router-link class="r-link" to="/">About</router-link> |
            <router-link class="r-link" to="/experience">Experience</router-link> |
            <router-link class="r-link" to="/samples">Work Samples</router-link> |
            <router-link class="r-link" to="/contact">Contact</router-link>
        </div>
    </div>
</template>

<style scoped>
    .r-link{
        margin-left:10px;
        margin-right:10px;
    }
    .header_frame{
        background-color:rgb(69, 212, 198);;
    }

    h1 {
        text-align: right;
        padding-right:5%;
        padding-left:5%;
        padding-top: 5%;
    }

    #header_frame {
        width:100%;
        height:10%;
    }

    .nav {
        padding-bottom: 10px;
        margin:auto;
        padding-left: 2%;
    }

    .nav a {
        font-weight: bold;
        color: #2c3e50;
        text-decoration:wavy;
    }

    .nav a.router-link-exact-active {
        color: #ffffff;
        text-decoration: none;
    }
</style>
