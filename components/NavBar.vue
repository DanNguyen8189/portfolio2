<template>
    <div class='nav'>
        <nuxt-link to='/' class='brand'>
           <i class="fas fa-home"></i>
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
            <!--<nuxt-link to='/resume.pdf' class='nav-link'>
                Resume
            </nuxt-link>-->
            <a href='resume.pdf' class='nav-link' target='_blank'>
                Resume
            </a> |     
            <nuxt-link :to="{ path: '/', hash: '#contact'}" class='nav-link'>
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
    z-index: 2;
    top: 0;
    left: 0;
    right: 0;
    //@at-rootbackground-color: map-get($colors, 'background');
    backdrop-filter: blur(30px);
}
.brand {
    margin-right: auto;
    margin-left: 2rem;
    font-size: 3rem;
    color: map-get($colors, "accent1");
}
nav {
    margin: 2rem;
    color: map-get($colors, 'accent1');
    :hover {
        color: map-get($colors, 'accent2');
    }
}
.nav-link {
    margin: 0 2rem;
    color: map-get($colors, 'accent1');
    font-weight: bold;
    text-decoration: none;
    transition: color .5s;
}
/*.nuxt-link {
    color: map-get($colors, "yellow");
}*/
/*.nuxt-link-active {
    color: map-get($colors, "yellow");
}*/
</style>