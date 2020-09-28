<template>    
    <!--<div class='center-align-container'>
        <div class='left-align-container'>
            <h1>Project1</h1>
            <p>project text!!!!a asdfasdf</p>
        </div>
    </div>-->
    <!--<div class='content'>-->
        <div id= 'featured-project-container' :class="orientation % 2 == 0 ? 'left-orientation' : 'right-orientation'">
        <!--<div class='left-orientation' id= 'featured-project-container'>-->
            <div id='project-info-container'>
                <div id='icons'>
                    <h1>{{ project.title }}</h1>
                    <a v-if="project.github != null" :href="project.github"><i class="fab fa-github"></i></a>
                    <a v-if="project.link != null" :href="project.link"><i class="fas fa-external-link-alt"></i></a>
                </div>
                <p>{{ project.description }}</p>
                <div id='technologies-list'>
                    <div v-for='technology in project.technologies' :key='technology'>
                        <p>{{ technology }}</p>
                    </div>
                </div>
            </div>
            <!--<div id='img-container'>-->
                <!--<img src='~static/hotspotify-screenshot.jpg'/>-->
                <!--<img :src="require(`@/static/${'hotspotify-screenshot.jpg'}`)">-->
                <img :src='getSrc()'/>
            <!--</div>-->
        </div>
    <!--</div>-->
</template>

<script>
export default {
    props: [
        'project',
        'orientation'
    ],
    methods: {
        // get image url for this project
        getSrc: function () {
            //console.log("image link: " + "~static/" + this.project.img);
            //console.log("image link2: " + "require(`@/static/${'hotspotify-screenshot.jpg'}`)");
            //return "~static/" + this.project.img;
            // return "require(`@/static/${'hotspotify-screenshot.jpg'}`)";

            // shorthand for 'require.context'. Using require.context, you force the 
            // files to be seen by webpack and resolve to the resulting image when setting src dynamically
            return require('../static/' + this. project.img);
        }
    },
};
</script>

<style scoped lang='scss'>
h1 {
    color: map-get($colors, 'accent1');
}
#featured-project-container {
    /*display: flex;
    flex-direction: column;*/
    margin-bottom: (5 * map-get($spacing, 'project-margin'));
    /*@media screen and (min-width: map-get($breakpoints, large)) {
        flex-direction: row;
    }*/
}
.left-orientation {
    display: flex;
    flex-direction: column;
    @media screen and (min-width: map-get($breakpoints, large)) {
        flex-direction: row;
    }
}
.right-orientation {
    display: flex;
    flex-direction: column;
    @media screen and (min-width: map-get($breakpoints, large)) {
        flex-direction: row-reverse;
    }
}
#project-info-container {
    display: flex;
    flex-direction: column;
    margin: 0;
    text-align: left;
    background: map-get($colors, 'block1');
    padding: 3rem;
    p {
        font-size: 1.5rem;
    }
}

#icons {
    display: flex;
    width: 100%;
    justify-content: flex-end;
    font-size: 2rem;
    margin-bottom: 2rem;
    h1 {
        font-size: 2.5rem;
        align-self: flex-start;
        margin-right: auto;
    }
    a {
        transition: color .5s;
        margin-left: 2rem;
    }
    a, a:visited, a:active {
        color: inherit;
    }
    a:hover {
        color: map-get($colors, 'accent2');
    }
}

#technologies-list {
    align-self: flex-end;
    margin-top: auto;
    display: flex;
    p {
        margin: 2rem 0 0 2rem;
    }
}

/*#img-container {
    width: 60%;
    img {
        width: 100%;
    }
}*/

img {
    width: 100%;
    @media screen and (min-width: map-get($breakpoints, large)) {
        width: 70%;
    }
}
</style>
