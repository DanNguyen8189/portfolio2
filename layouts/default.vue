<template>
    <div id='app'>
        <nav-bar id='nav-bar'/>
        <hamburger-nav id='hamburger-nav'/>
        <Nuxt />
    </div>
</template>

<script>
//import NavBar from '~/components/NavBar.vue';
import NavBar from '~/components/NavBar.vue';
import HamburgerNav from '~/components/HamburgerNav.vue';
export default {
    components: {
        NavBar,
        HamburgerNav
    }
}
</script>

<style lang='scss'>
html {
    font-family:
        'Source Sans Pro',
        -apple-system,
        BlinkMacSystemFont,
        'Segoe UI',
        Roboto,
        'Helvetica Neue',
        Arial,
        sans-serif;
    //font-size: 10px;
    font-size: map-get($font-sizes, "medium"); 
    word-spacing: 1px;
    -ms-text-size-adjust: 100%;
    -webkit-text-size-adjust: 100%;
    -moz-osx-font-smoothing: grayscale;
    -webkit-font-smoothing: antialiased;
    box-sizing: border-box;
    scroll-behavior: smooth; 
    /*@media screen and (max-width: map-get($breakpoints, small)) {
        font-size: map-get($font-sizes, "small");
    }*/
}

*,
*::before,
*::after {
    box-sizing: border-box;
    margin: 0;
}

#app {
    background-color: map-get($colors, "background");
    //background: rgb(38,70,83);
    //background: linear-gradient(180deg, rgba(38,70,83,1) 0%, rgba(164,165,129,1) 100%);
    //background-attachment: fixed;
    color: map-get($colors, "text-default");
}

// display settings for both kinds of menus
@media screen and (min-width: map-get($breakpoints, medium)) {
    #hamburger-nav {
        display: none;
    }
}

@media screen and (max-width: map-get($breakpoints, medium)) {
    #nav-bar {
        display: none;
    }
}


/*#nav-bar {
    position: fixed;
}*/
.button--green {
    display: inline-block;
    border-radius: 4px;
    border: 1px solid #3b8070;
    color: #3b8070;
    text-decoration: none;
    padding: 10px 30px;
}

.button--green:hover {
    color: #fff;
    background-color: #3b8070;
}

.button--grey {
    display: inline-block;
    border-radius: 4px;
    border: 1px solid #35495e;
    color: #35495e;
    text-decoration: none;
    padding: 10px 30px;
    margin-left: 15px;
}

.button--grey:hover {
    color: #fff;
    background-color: #35495e;
}
</style>
