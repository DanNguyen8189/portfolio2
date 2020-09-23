<template>
    <div class='nav'>
        <nuxt-link to='/' class='brand'>
           Home
        </nuxt-link>
        <nav>
            <!--<a href="#aboutme">About Me</a>-->
            <!--resume link insert here-->
            <nuxt-link :to="{ path: '/', hash: '#aboutme'}">
                About Me
            </nuxt-link>
            <nuxt-link :to="{ path: '/', hash: '#projects'}">
                Projects
            </nuxt-link>            
            <nuxt-link to='/contact'>
                Contact
            </nuxt-link>
        </nav>
    </div>
</template>
<style scoped lang='scss'>
    nuxt-link {
        color: map-get($colors, "orange");
    }
</style>