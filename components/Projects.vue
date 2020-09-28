<template>    
    <div id='projects' class='content'>
        <div class='left-align-container'>
            <h1 class='section-title'>Some Projects I've Done</h1>
            <!--<h2>{{ projects[0].title }}</h2>-->
            <!--<featured-project :project='projects[0]'/>
            <featured-project :project='projects[1]'/>-->
            <div v-for='n in projects.length' v-if='projects[n-1].img != null' :key='n'>
                <featured-project :project='projects[n-1]' :orientation='n'/>
            </div>
            <!--<div v-for='project in projects' v-if='project.featured == true' :key='project.title'>
                <featured-project :project='project'/>
            </div>-->
        </div>
        <!--<div class='project-grid'>
            <basic-project :project='projects[0]'/>
            <basic-project :project='projects[0]'/>
            <basic-project :project='projects[0]'/>
            <basic-project :project='projects[0]'/>
        </div>-->
        <div class='project-grid'>
        <div v-for='project in projects' v-if='project.img == null' :key='project.title' class='basic-project'>
            <!--<basic-project :title="projects[n-1].title" :description="projects[n-1].description" 
                :github="projects[n-1].github" :technologies="projects[n-1].technologies"/>-->
            <basic-project :project='project'/>
        </div>
        </div>
    </div>
</template>

<script>
import FeaturedProject from '~/components/FeaturedProject.vue';
import BasicProject from '~/components/BasicProject.vue';
export default {
    props: [
        'projects'
    ],
    /*computed: {
        nonFeaturedProjects: ()=> {
            return projects.filter(function(project){
                return project.featured == false;
            })
        }
    }*/
};
</script>

<style scoped lang='scss'>
/*.left-align-container {
    background-color: purple;
}*/
.content {
    flex-direction: column;
}
/*.project-grid {
    display: flex;
    align-items: flex-start;
    flex-wrap: wrap;
    justify-content: space-between;
}
.basic-project {
    flex-basis: 100%;
    @media screen and (min-width: map-get($breakpoints, medium)) {
        //flex-basis: 49%;
        flex: 1 1 50%;
    }
}*/

.project-grid {
    display: flex;
    //align-items: flex-start;
    align-items: stretch;
    flex-wrap: wrap;
    //justify-content: space-between;
    
    margin: (-1 * map-get($spacing, 'project-margin')) (-1 *map-get($spacing, 'project-margin'));
}
.basic-project {
    display: flex;
    align-items: stretch;
    // width: calc(100% - 14px);
    width: calc(100% - 2 * #{map-get($spacing, 'project-margin')});
    margin: map-get($spacing, 'project-margin');
    @media screen and (min-width: map-get($breakpoints, medium)) {
        //flex-basis: 49%;
        //flex: 1 1 50%;
        width: calc(50% - 2 * #{map-get($spacing, 'project-margin')});
    }
}
</style>