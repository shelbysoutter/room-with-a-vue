<template>
    <div class="footer-container">
        <div class="content-wrap">
            <div class="footer">
                <img src="https://www.themoviedb.org/assets/2/v4/logos/v2/blue_square_1-5bdc75aaebeb75dc7ae79426ddd9be3b2be1e342510f8202baf6bffa71d7f5c4.svg" style="width:50px;height:50px">
                <p>"This product uses the TMDb API but is not endorsed or certified by TMDb."</p>
            </div>
        </div>
    </div>
</template>

<script>
export default {
    name: "Footer"
}
</script>

<style scoped>
    .footer {
        background: #424954;
        color: #fff;
        text-align: center;
        position: absolute;
        padding: 20px;
        padding-left: 50px;
        width: 100%;
        left: 0;
        bottom: 0;
        display: flex;
        justify-content: center;
    }
    .footer-container {
        position: relative;
        /* min-height: 20vh; */

    }
</style>