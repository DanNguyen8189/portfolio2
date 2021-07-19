<template>    
    <div id='aboutme' class='content'>
        <div class='left-align-container'>
            <h1 class='section-title'>About Me</h1>
            <p>Hello! I'm Dan, a software developer from Los Angeles, California.</p>
            <p>I graduated from UC San Diego with a B.S. in computer science. 
                During my time there, I discovered my interest in the field, solving problems and 
                making things come to life. I learned a lot from my time in school - from coursework, working in 
                group projects, and contributing in student organizations. I look forward to learning more in the industry!</p>
            <p>In my free time, I like illustrating and and posting my artwork on the web. I also enjoy playing soccer and basketball.</p>
            <p>Some technologies I've worked with:</p>
            <ul>
                <li>Python</li>
                <li>Java</li>
                <li>C / C++</li>
                <li>C#</li>
                <li>JavaScript</li>
                <li>Vue / React</li>
                <li>HTML / CSS</li>
            </ul>
        </div>
    </div>
</template>

<script>
export default {};
</script>
<style scoped lang='scss'>

/* The about me portion consists of a paragraph with a description about me and a 2-column list of technologies I've used below it */
#aboutme {
    font-size: 1.5rem;
    p {
    //font-size: 1.5rem;
    margin-bottom: 2em;
    }
    ul {
        columns: 2;
        -webkit-columns: 2;
        -moz-columns: 2;
        //font-size: 1.5em;
        li {
            margin-bottom: .5em;
        }
    }
}

</style>
