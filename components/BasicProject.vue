<template>    
    <div class='left-align-container'>
        <h1>{{ project.title }}</h1>
        <p>{{ project.description }}</p>
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
.left-align-container {
    flex-basis: 40rem;
    background: map-get($colors, "darkgreen");
    padding: 10px;
    margin: 10px 0;
    border-radius: 5px;
    @media screen and (min-width: map-get($breakpoints, large)) {
        padding: 30px;
        margin: 10px;
    }
}
h1 {
    color: map-get($colors, "orange");
}
</style>
