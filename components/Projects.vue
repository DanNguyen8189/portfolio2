<template>    
    <div id='projects' class='content'>
        <div class='left-align-container'>
            <h1 class='section-title'>Some Projects I've Done</h1>
            <!--<h2>{{ projects[0].title }}</h2>-->
            <!--<featured-project :project='projects[0]'/>
            <featured-project :project='projects[1]'/>-->
            <div v-for='project in projects' v-if='project.featured == true' :key='project.title' class='project-grid'>
                <featured-project :project='project'/>
            </div>
        </div>
        <div class='project-grid'>
            <!--<basic-project :title="projects[1].title" :description="projects[1].description" 
            :github="projects[1].github" :technologies="projects[1].technologies"/>
            <basic-project/>-->
        </div>
        <div v-for='project in projects' v-if='project.featured == null' :key='project.title' class='project-grid'>
            <!--<basic-project :title="projects[n-1].title" :description="projects[n-1].description" 
                :github="projects[n-1].github" :technologies="projects[n-1].technologies"/>-->
            <basic-project :project='project'/>
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
.project-grid {
    display: flex;
    align-items: flex-start;
    flex-wrap: wrap;
}
/*.left-align-container {
    flex: 100%;
}
.center-align-container {
    flex: 100%;
}*/
</style>