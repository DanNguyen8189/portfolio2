<template>    
    <div id='contact' class='content'>
        <div class='center-align-container'>
            <h1 class='section-title'>Get in touch!</h1>
            <p id='contact-text'>I'm available via email at dannguyen8189@gmail.com</p>
            <a href="mailto:dannguyen8189@gmail.com"><button>Send Email</button></a>
            <div id='credits-section'>
                <p>Landing page background image by @adrienconverse on Unsplash</p>
                <p>Website built by me! Source code can be found <a href='https://github.com/DanNguyen8189/portfolio2'>here</a></p>
            </div>
        </div>
    </div>
</template>

<script>
export default {};
</script>
<style scoped lang='scss'>
.center-align-container {
    margin: 0 auto;
    display: flex;
    flex-direction: column;
    justify-content: center;
    align-items: center;
    text-align: center;
    #contact-text {
        font-size: 2rem;
        margin-bottom: 4rem;
    }

    /* Send email button */
    button {
        padding: 2rem;
        cursor: pointer;
        background-color: map-get($colors, 'block1');
        border: none;
        color: map-get($colors, 'accent1');
        transition: color 1s;
    }
    button:hover {
        color: map-get($colors, 'accent2');
    }

    #credits-section {
        font-size: 1.2rem;
        margin-top: auto;
    }
}
a:visited {
    color: inherit;
}
</style>
