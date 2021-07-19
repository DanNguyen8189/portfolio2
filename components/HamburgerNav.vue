<template>
    <div class="menu-wrap">
        <input type="checkbox" class="toggler" v-model="checked">
        <div class="hamburger"><div></div></div>
        <div class="menu">
            <div>
                <div>
                    <ul>
                        <!--wrapping these in <li> seems to let use use @click-->
                        <li @click='toggleMenu()'><nuxt-link :to="{ path: '/' }" class='nav-link'>
                            Home
                        </nuxt-link></li>
                        <li @click='toggleMenu()'><nuxt-link :to="{ path: '/', hash: '#aboutme'}" class='nav-link'>
                            About Me
                        </nuxt-link></li>
                        <li @click='toggleMenu()'><nuxt-link :to="{ path: '/', hash: '#projects'}" class='nav-link'>
                            Projects
                        </nuxt-link></li>
                        <li @click='toggleMenu()'><a href='resume.pdf' class='nav-link' target='_blank'>
                            Resume
                        </a></li>
                        <li@click='toggleMenu()'><nuxt-link :to="{ path: '/', hash: '#contact'}" class='nav-link'>
                            Contact
                        </nuxt-link></li>
                    </ul>
                </div>
            </div>
        </div>
    </div>
</template>

<script>
export default {
    methods: {
        // whenever someone clicks a menu item the menu closes
        toggleMenu: function () {
            this.checked = !this.checked;
        }
    },
    data() {
        return {
            // this is used for closing the menu when someone clicks a menu item
            checked: false
        }
    }
};
</script>

<style scoped lang='scss'>
*{
    box-sizing: border-box;
    margin: 0;
    padding: 0;
}
body{
    // font-family: 'Staatliches', cursive;
    line-height: 1.4;
}
.menu-wrap{
    position: fixed;
    top: 0;
    left: 0;
    z-index: 1;
}
.menu-wrap .toggler{
    position: absolute;
    top: 0;
    left: calc(100vw - 60px);
    z-index: 2;
    cursor: pointer;
    width: 60px;
    height: 60px;
    opacity: 0;
}
.menu-wrap .hamburger{
    position: absolute; /* hamburger menu sits at the top right; position: absolute allows us to do this */
    top: 0;
    left: calc(100vw - 60px); /* we don't want the hamburger to hug the right side, but just be close to it*/
    z-index: 1;
    width: 60px;
    height: 60px;
    padding: 1.6rem;
    background: map-get($colors, 'block1');
    display: flex; /* lets us set up the hamburger menu lines down the middle using align-items and justify-content*/
    align-items: center; 
    justify-content: center;
}
/* Middle hamburger line */
.menu-wrap .hamburger > div {
    position: relative; /* lets us position: absolute the other 2 hamburger lines off of this one */
    width: 100%;
    height: 3px;
    background-color: #fff;
    display: flex;
    align-items: center;
    justify-content: center;
    transition: all 0.4s ease; /* toggle animation speed for the menu */
}
/* duplicate line to form top and bottom lines of the hamburger */
.menu-wrap .hamburger > div:before,
.menu-wrap .hamburger > div:after{
    content: '';
    position: absolute;
    z-index: 1;
    top: -10px; /* move a line up to form the top hamburger line */
    width: 100%;
    height: 3px;
    background: inherit;
}
/* Moves one of the lines down to form the bottom line */
.menu-wrap .hamburger > div:after{
    top: 10px;
}

/* Animate when user clicks it */
.menu-wrap .toggler:checked + .hamburger > div{
    transform: rotate(135deg);
    background: map-get($colors, 'accent1');
}
/* Turn hamburger lines into an X shape on click */
.menu-wrap .toggler:checked + .hamburger > div:before,
.menu-wrap .toggler:checked + .hamburger > div:after{
    top: 0;
    transform: rotate(90deg);
}
/* Rotate on hover when checked */
.menu-wrap .toggler:checked:hover + .hamburger > div{
    transform: rotate(225deg);
}
/* Show menu */
.menu-wrap .toggler:checked ~ .menu{
    visibility: visible; /* Menu shows up when user clicks the hamburger button */
}
.menu-wrap .toggler:checked ~ .menu > div{
    transform: scale(1); /* Expand menu from its initial invisible state on  click */
    transition-duration: .75s;
}
.menu-wrap .toggler:checked ~ .menu > div > div{
    opacity: 1;
    transition: opacity 0.4s ease;
}

/* the menu. It expands from the center from size zero when user clicks the hamburger button and shrinks back to size zero when user clicks 'x' */
.menu-wrap .menu{
    position: fixed; /* menu should show up at same spot regardless of where user has scrolled */
    top: 0;
    left: 0;
    width: 100%;
    height: 100%;
    font-weight: 700;
    visibility: hidden; /* menu starts out hidden */
    overflow: hidden;
    display: flex;
    align-items: center;
    justify-content: center;
}
.menu-wrap .menu > div{
    background-color: rgba(24,39,51,0.85);
    border-radius: 50%; /* menu is enclosed in a circle */
    width: 200vh;
    height: 200vh;
    display: flex;
    flex: none;
    align-items: center;
    justify-content: center;
    transform: scale(0); /* menu starts out at size zero before growing when user wants to see it */
    transition: all 0.4s ease; /* the speed the menu grows and shrinks */
    @media screen and (min-width: map-get($breakpoints, large)) {
        width: 200vw;
        height: 200vw;
    }
}

/* the menu text */

.menu-wrap .menu > div > div{
    text-align: center;
    max-width: 90vw;
    max-height: 100vh;
    opacity: 0; 
    transition: opacity 0.4s ease;
}
.menu-wrap .menu > div > div > ul > li {
    list-style: none;
    color: map-get($colors, 'accent1');
    font-size: 3rem;
    padding: 1rem;
}

.menu-wrap .menu >div > div > ul > li > a{
    color: inherit;
    text-decoration: none;
    transition: color 0.4s ease;
}
.menu-wrap .menu > div > div > ul > li > a:hover {
    color: map-get($colors, 'accent1');
}
</style>
