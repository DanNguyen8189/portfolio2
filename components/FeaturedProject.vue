<template>    
    <!--<div class='center-align-container'>
        <div class='left-align-container'>
            <h1>Project1</h1>
            <p>project text!!!!a asdfasdf</p>
        </div>
    </div>-->
    <!--<div class='content'>-->
        <div class='left-align-container'>
            <h1>Featured Project</h1>
            <p>project text!!!!a asdfasdf asdf asdf asdf adf  asdaef  asf asf aef  asf</p>
        </div>
    <!--</div>-->
</template>

<script>
export default {};
</script>

<style scoped lang='scss'>
.left-align-container {
    background: map-get($colors, "darkgreen");
    padding: 10px;
    margin: 10px 0;
    border-radius: 5px;
    @media screen and (min-width: map-get($breakpoints, large)) {
        padding: 30px;
    }
}
h1 {
    color: map-get($colors, "orange");
}
</style>
