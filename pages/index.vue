<template>
<div>
    <!--<nuxt-link to='/' class='brand'>
        Oh yea baby
    </nuxt-link>-->
    <div id='landingpage' class='content'>
        <div class='center-align-container'>
            <div class='left-align-container'>
                <p>Hello, my name is</p>
                <!--<div class="break">uh</div>--> <!-- break -->
                <h1 class='name'>Dan Nguyen</h1>
                <p>Welcome to my site! I'm a newly graduated software developer 
                    looking for my first full-time role. Can I interest you in some projects of mine?</p>
            </div>
        </div>
    </div>
    <!--<div id='aboutme' class='page'>
        <div class='left-align-container'>
            <h1 class='section-title'>About Me</h1>
            <p>About me text</p>
        </div>
    </div>-->
    <about-me/>
    <projects/>
</div>
</template>

<script>
import AboutMe from '~/components/AboutMe.vue';
import Projects from '~/components/Projects.vue';
export default {};
</script>

<style lang='scss'>
.section-container {
    margin: 0 auto;
    min-height: 100vh;
    max-width: 100vw;
    display: flex;
    justify-content: center;
    align-items: center;
    text-align: center;
}

.content {
    min-height: 100vh;
    max-width: 100vw;
    padding: 50px 8%;
    display: flex;
    //align-items: flex-start;
    /*justify-content: center;
    align-items: center;
    text-align: center;*/
    @media screen and (min-width: map-get($breakpoints, large)) {
        padding: 50px 15%;
    }
}
#landingpage {
    justify-content: center;
    align-items: center;
    text-align: center;
}

// containers used in other components
.center-align-container {
    margin: 0 auto;
    display: flex;
    justify-content: center;
    align-items: center;
    text-align: center;
}
.left-align-container {
    display: flex;
    flex-direction: column;
    margin: 0;
    text-align: left;
    p {
        font-size: 2rem;
    }
}
/*.left-align-container p{
    flex-basis: 100%;
    background: red;
}*/

.name {
    font-family: "Quicksand", "Source Sans Pro", -apple-system, BlinkMacSystemFont,
      "Segoe UI", Roboto, "Helvetica Neue", Arial, sans-serif;
    display: block;
    font-weight: 300;
    font-size: 8rem;
    //color: #35495e;
    // color: $green;
    color: map-get($colors, "orange");
    letter-spacing: 1px;
    margin: 20px 0;
}

.section-title {
    font-weight: 300;
    font-size: 5rem;
    //color: #526488;
    color: map-get($colors, "yellow");
    word-spacing: 5px;
    padding-bottom: 15px;
}

.links {
    padding-top: 15px;
}
</style>
