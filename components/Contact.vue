<template>    
    <div id='contact' class='content'>
        <div class='center-align-container'>
            <h1 class='section-title'>Get in touch!</h1>
            <p>I'm available via email at dannguyen8189@gmail.com</p>
            <a href="mailto:dannguyen8189@gmail.com"><button>Send Email</button></a>
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
    p {
        font-size: 2rem;
        margin-bottom: 4rem;
    }

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
}
</style>