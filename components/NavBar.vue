<template>
    <div class='nav'>
        <nuxt-link to='/' class='brand'>
           Home
        </nuxt-link>
        <nav>
            <!--<a href="#aboutme">About Me</a>-->
            <!--resume link insert here-->
            <nuxt-link :to="{ path: '/', hash: '#aboutme'}" class='nav-link'>
                About Me
            </nuxt-link> | 
            <nuxt-link :to="{ path: '/', hash: '#projects'}" class='nav-link'>
                Projects
            </nuxt-link> |     
            <nuxt-link to='/' class='nav-link'>
                Resume
            </nuxt-link> |     
            <nuxt-link to='/contact' class='nav-link'>
                Contact
            </nuxt-link>
        </nav>
    </div>
</template>
<style scoped lang='scss'>
.nav {
    display: flex;
    align-items: center;
    justify-content: flex-end;
    font-size: 1.5rem;
    position: fixed;
    top: 0;
    left: 0;
    right: 0;
    background-color: map-get($colors, "slateblue");
    backdrop-filter: blur(20px);
}
.brand {
    margin-right: auto;
    margin-left: 2rem;
}
nav {
    margin: 2rem;
    color: map-get($colors, "orange");
}
.nav-link {
    margin: 0 2rem;
    color: map-get($colors, "orange");
    font-weight: bold;
    text-decoration: none;
}
/*.nuxt-link {
    color: map-get($colors, "yellow");
}*/
/*.nuxt-link-active {
    color: map-get($colors, "yellow");
}*/
</style>