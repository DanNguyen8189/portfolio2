<template>    
    <div class='left-align-container'>
        <h1>Basic Project</h1>
        <p>project text!!!! af asdf asdf asfd asdf asdf as dfa sdfasd asdf  af asdf  asdf a asf asfasf</p>
    </div>
</template>

<script>
export default {};
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
