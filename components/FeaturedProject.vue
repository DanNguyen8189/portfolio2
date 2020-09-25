<template>    
    <!--<div class='center-align-container'>
        <div class='left-align-container'>
            <h1>Project1</h1>
            <p>project text!!!!a asdfasdf</p>
        </div>
    </div>-->
    <!--<div class='content'>-->
        <div class='left-align-container'>
            <h1>{{ project.title }}</h1>
            <p>{{ project.description }}</p>
            <div id='technologies-list'>
                <div v-for='technology in project.technologies' :key='technology'>
                    <p>{{ technology }}</p>
                </div>
            </div>
        </div>
    <!--</div>-->
</template>

<script>
export default {
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
.left-align-container {
    background: map-get($colors, "darkgreen");
    padding: 10px;
    margin: (2 * map-get($spacing, 'project-margin')) 0;
    @media screen and (min-width: map-get($breakpoints, large)) {
        padding: 30px;
    }
}
#technologies-list {
    align-self: flex-end;
    margin-top: auto;
    display: flex;
    p {
        opacity: 70%;
        margin: 2rem 0 0 2rem;
    }
}
</style>
