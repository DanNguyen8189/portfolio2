<template>    
    <div id='projects' class='content'>
        <div class='left-align-container'>
            <h1 class='section-title'>Some Projects I've Done</h1>
            <h2>{{ projects[0].title }}</h2>
            <featured-project/>
            <featured-project/>
        </div>
        <div class='project-grid'>
            <basic-project/>
            <basic-project/>
            <basic-project/>
        </div>
    </div>
</template>

<script>
import FeaturedProject from '~/components/FeaturedProject.vue';
import BasicProject from '~/components/BasicProject.vue';
export default {
    props: [
        'projects'
    ]
};
</script>

<style scoped lang='scss'>
/*.left-align-container {
    background-color: purple;
}*/
.content {
    flex-direction: column;
}
.project-grid {
    display: flex;
    align-items: space-between;
    flex-wrap: wrap;
}
/*.left-align-container {
    flex: 100%;
}
.center-align-container {
    flex: 100%;
}*/
</style>