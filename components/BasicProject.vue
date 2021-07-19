<template>    
    <div id='basic-project-container'>
        <div id='icons'>
            <i class="fas fa-cog"></i>
            <a v-if="project.github != null" :href="project.github"><i class="fab fa-github"></i></a>
            <a v-if="project.link != null" :href="project.link"><i class="fas fa-external-link-alt"></i></a>
        </div>
        <h1>{{ project.title }}</h1>
        <p>{{ project.description }}</p>
        <div id='technologies-list'>
            <div v-for='technology in project.technologies' :key='technology'>
                <p>{{ technology }}</p>
            </div>
        </div>
    </div>
</template>

<script>
export default {
    /*props: [
        'title',
        'description',
        'github',
        'technologies'
    ]*/
    props: [
        'project'
    ]
};
</script>

<style scoped lang='scss'>
/* Basic projects are the projects that don't have an image associated with them */
h1 {
    color: map-get($colors, 'accent1');
    margin-bottom: 2rem;
}
p {
    font-size: 1.5rem;
}
#basic-project-container {
    display: flex;
    flex-direction: column; /* aligns each section one on top of the other */
    margin: 0;
    text-align: left; /* left aligns the description and title */
    width: 100%;
    background: map-get($colors, 'block1');
    padding: 3rem;
    p {
        margin-bottom: 3rem; /* adds space underneath for aesthetic purposes */
    }
    //margin: 5px 0;
    @media screen and (min-width: map-get($breakpoints, large)) {
        padding: 3rem;
        //margin: 5px;
    }
}

/* external links (ex github) located at the top*/
#icons {
    display: flex;
    width: 100%;
    justify-content: flex-end; /* lines the icons up at the right side */
    font-size: 2rem;
    margin-bottom: 1rem;
    .fa-cog {
        align-self: flex-start; /* breaks the cog symbol out of the other right aligned icons so it can sit on the left for design purposes */
        margin-right: auto;
        font-size: 3rem;
    }
    a {
        transition: color .5s; /* slowly change color as user hovers over the link */
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
    align-self: flex-end; /* technologies list sits at the bottom right*/
    margin-top: auto;
    display: flex;
    p {
        margin: 0 0 0 2rem; /* spaces each technology so they're not too close to each other */
    }
}
</style>
