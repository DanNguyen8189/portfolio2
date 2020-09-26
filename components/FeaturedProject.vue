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
                <h1>{{ project.title }}</h1>
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
        // whenever someone clicks a menu item the menu closes
        getSrc: function () {
            console.log("image link: " + "~static/" + this.project.img);
            console.log("image link2: " + "require(`@/static/${'hotspotify-screenshot.jpg'}`)");
            //return "~static/" + this.project.img;
            // return "require(`@/static/${'hotspotify-screenshot.jpg'}`)";
            return require('../static/' + this. project.img);
        }
    },
};
</script>

<style scoped lang='scss'>
h1 {
    color: map-get($colors, "orange");
}
#featured-project-container {
    /*display: flex;
    flex-direction: column;*/
    margin: (2 * map-get($spacing, 'project-margin')) 0;
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
.right-orienation {
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
    background: map-get($colors, "darkgreen");
    padding: 10px;
    p {
        font-size: 1.5rem;
    }
    @media screen and (min-width: map-get($breakpoints, large)) {
        padding: 30px;
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
    @media screen and (min-width: map-get($breakpoints, medium)) {
        width: 70%;
    }
}
</style>
