<template>
<div>
    <nuxt-link to='/' class='brand'>
        Oh yea baby
    </nuxt-link>
    <a href="#anchor2">Jump to second half</a>
    <div id='anchor1' class="container">
        <h1 class='title'>hey</h1>
    </div>
    <div id='anchor2' class='container'>
        <h1 class='title'>Yes!!!</h1>
        <a href="#anchor1">Back to the top</a>
    </div>
</div>
</template>

<script>
export default {};
</script>

<style lang='scss'>
.container {
    margin: 0 auto;
    min-height: 100vh;
    display: flex;
    justify-content: center;
    align-items: center;
    text-align: center;
}

.page {
    min-height: 100vh;
    min-width: 100vw;
    display: flex;
    justify-content: center;
    align-items: center;
    text-align: center;
}

.title {
    font-family: "Quicksand", "Source Sans Pro", -apple-system, BlinkMacSystemFont,
      "Segoe UI", Roboto, "Helvetica Neue", Arial, sans-serif;
    display: block;
    font-weight: 300;
    font-size: 10rem;
    //color: #35495e;
    color: $green;
    letter-spacing: 1px;
}

.subtitle {
    font-weight: 300;
    font-size: 42px;
    color: #526488;
    word-spacing: 5px;
    padding-bottom: 15px;
}

.links {
    padding-top: 15px;
}
</style>
