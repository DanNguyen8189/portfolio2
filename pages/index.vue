<template>
<div>
    <!--<nuxt-link to='/' class='brand'>
        Oh yea baby
    </nuxt-link>-->
    <div id='landingpage' class='content'>
        <div class='center-align-container'>
            <div class='left-align-container'>
                <p class='landing-page-text' style="--animation-order: 1;">Hello, my name is</p>
                <!--<div class="break">uh</div>--> <!-- break -->
                <h1 class='name' style="--animation-order: 2;">Dan Nguyen</h1>
                <p class='landing-page-text' style="--animation-order: 3;">Welcome to my site! I'm a recently graduated software developer 
                    looking for my first role. Can I interest you in some projects of mine?</p>
                <ul class='social_media'>
                    <li id='linkedin' style="--animation-order: 5;">
                        <a href="https://www.linkedin.com/in/dannguyen8189/" target="_blank">
                            <i class='fab fa-linkedin-in' aria-hidden='true'></i>
                        </a>
                    </li>
                    <li id="github" style="--animation-order: 6;">
                        <a href="https://github.com/DanNguyen8189" target="_blank">
                            <i class='fab fa-github' aria-hidden='true'></i>
                        </a>
                    </li>
                    <li id='dev-to' style="--animation-order: 7;">
                        <a href="https://dev.to/danimalphantom" target="_blank">
                            <i class='fab fa-dev' aria-hidden='true'></i>
                        </a>
                    </li>
                </ul>
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
    <projects :projects="projects"/>
    <contact/>
</div>
</template>

<script>
import AboutMe from '~/components/AboutMe.vue';
import Projects from '~/components/Projects.vue';
import Contact from '~/components/Contact.vue';
export default {
    components: {
        Projects
    },
    data() {
        return {
            preciousThing: 'ring'
        }
    },
    async asyncData({ $content }) {
        let projects = await $content('projects').only(['projects']).fetch();
        //console.log(projects);
        //console.log("length: " + projects.length);
        projects = projects[0].projects;
        //console.log(projects);

        // console.log("title: " + projects[0].body.children[0].props.id);

        //console.log(projects[0][1].title);
        return {
            projects: projects
        }
    }
};
</script>

<style lang='scss'>

// Classes that can be used in child components

// Section layout
.section-container {
    margin: 0 auto;
    min-height: 100vh;
    max-width: 100vw;
    display: flex;
    justify-content: center;
    align-items: center;
    text-align: center;
}

.section-title {
    font-family: 'Poiret One', cursive;
    font-weight: 700;
    font-size: 4rem;
    //color: #526488;
    color: map-get($colors, 'accent1');
    word-spacing: 5px;
    margin-bottom: 5rem;
    margin-top: 5rem;
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

// Other useful classes
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
} 

// landing page styling
#landingpage {
    justify-content: center;
    align-items: center;
    text-align: center;
    //background: url("~@/static/unsplash-adrienconverse.jpg");
    background: linear-gradient(rgba(32, 59, 70, 0.85), rgba(32, 59, 70, 0.85)),
  url("~@/static/unsplash-adrienconverse.jpg"); /*background image + tint*/
    -webkit-background-size: cover;
    -moz-background-size: cover;
    -o-background-size: cover;
    background-size: cover;
    background-position: center;
}

.name {
    /*font-family: "Quicksand", "Source Sans Pro", -apple-system, BlinkMacSystemFont,
      "Segoe UI", Roboto, "Helvetica Neue", Arial, sans-serif;*/
    font-family: 'Poiret One', cursive;
    display: block;
    //font-weight: 300;
    font-weight: 700;
    font-size: 6rem;
    //color: #35495e;
    // color: $green;
    color: map-get($colors, 'accent1');
    letter-spacing: 1px;
    margin: 20px 0;
    animation-name: animateName;
    animation-duration: 2s;
    animation-delay: calc(var(--animation-order) * 200ms);
    animation-fill-mode: both;
    animation-timing-function: ease-in-out;
}
@keyframes animateName {
  0% {
    opacity: 0;
    transform: translateX(30px);
  }
  
  100% {
    opacity: 1;
  }
}

.landing-page-text {
    font-size: 1.5rem;
    animation-name: animateLandingPageText;
    animation-duration: 2s;
    animation-delay: calc(var(--animation-order) * 200ms);
    animation-fill-mode: both;
    animation-timing-function: ease-in-out;
    @media screen and (min-width: map-get($breakpoints, large)) {
        font-size: 2rem;
    }
    
}
@keyframes animateLandingPageText {
  0% {
    opacity: 0;
    transform: translateX(30px);
  }
  
  100% {
    opacity: 1;
  }
}

.links {
    padding-top: 15px;
}

.social_media {
  /*position: absolute;
    top: 9rem;
    left: 50%;
    transform: translate(-50%, -50%); */
    display: block;
    margin-top: 5rem;
    margin-right: 0;
    margin-left: auto;
    text-align: center;
    padding: 0; /*needed to correectly center*/
    position: relative;
    color: black;
}
.social_media li {
    display: inline-block;
    list-style: none;
    position: relative;
    font-size: 3rem;
    margin-left: 1em;

    animation-name: animateSocialMedia;
    animation-duration: 1.5s;
    animation-delay: calc(var(--animation-order) * 150ms);
    animation-fill-mode: both;
    animation-timing-function: ease-in-out;
}

@keyframes animateSocialMedia {
  0% {
    opacity: 0;
    transform: scale(0.6) translateX(30px) rotate(180deg);
  }
  
  100% {
    opacity: 1;
  }
}

.social_media li a {
    //original width: 70 height: 40
    width: 1.75em;
    height: 1em;
    background: map-get($colors, 'text-default');
    display: block;
    text-align: center;
    line-height: 0px; //removing this breaks the mobile version?*
    font-size: 3rem;
    transition: 0.5s;
    color: black;
    opacity: 0.75;
    @media screen and (min-width: map-get($breakpoints, large)) {
        font-size: 4rem;
    }
}
.social_media li a:before {
    content: "";
    position: absolute;
    top: 0;
    left: 0;
    width: 100%;
    height: 100%;
    background: inherit;
    z-index: -1;
    transform: rotate(60deg);
}
.social_media li a:after {
    content: "";
    position: absolute;
    top: 0;
    left: 0;
    width: 100%;
    height: 100%;
    background: inherit;
    z-index: -1;
    transform: rotate(-60deg);
}

.social_media li a:hover {
    transition: transform 0.25s;
    transform: rotate(7deg);
    opacity: 1;
    /*color: #59316e;*/
    /*background: #aefade;*/
}

#linkedin a:hover {
    background: #007bb5;
    color: white;
}
#github a:hover {
    background: black;
    color: white;
}
#instagram a:hover {
    background: #c32aa3;
    color: white;
}
#twitter a:hover {
    background: #1da1f2;
    color: white;
}
#dev-to a:hover {
    background: black;
    color: white;   
}
/*On-click for social media buttons*/
.social_media li a:active {
    transition: transform 0.2s;
    transform: rotate(15deg) scale(0.9);
    opacity: 0.4;
}

</style>
