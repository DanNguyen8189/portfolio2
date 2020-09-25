<template>
    <div id='app'>
        <nav-bar id='nav-bar'/>
        <Nuxt />
    </div>
</template>

<script>
//import NavBar from '~/components/NavBar.vue';
import NavBar from '~/components/NavBar.vue';
export default {
    components: {
        NavBar
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
    @media screen and (max-width: map-get($breakpoints, small)) {
        font-size: map-get($font-sizes, "small");
    }
}

#app {
    background-color: map-get($colors, "slateblue");
    color: map-get($colors, "lightgreen");
}
*,
*::before,
*::after {
    box-sizing: border-box;
    margin: 0;
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
