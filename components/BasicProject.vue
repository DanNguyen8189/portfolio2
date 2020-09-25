<template>    
    <div id='basic-project-container'>
        <i class="fab fa-github"></i>
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
h1 {
    color: map-get($colors, "orange");
}
p {
    font-size: 1.5rem;
}
#basic-project-container {
    display: flex;
    flex-direction: column;
    margin: 0;
    text-align: left;
    width: 100%;
    background: map-get($colors, "darkgreen");
    padding: 10px;
    p {
        margin-bottom: 3rem;
    }
    //margin: 5px 0;
    @media screen and (min-width: map-get($breakpoints, large)) {
        padding: 30px;
        //margin: 5px;
    }
}
#technologies-list {
    align-self: flex-end;
    margin-top: auto;
    display: flex;
    p {
        opacity: 70%;
        margin: 0 0 0 2rem;
    }
}
</style>
