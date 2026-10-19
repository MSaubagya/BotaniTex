```vue
<template>
    <section class="container">

        <!-- About Us -->
        <div class="text-center mt-5 mb-5">
            <h1 class="fw-medium mb-4">About Us</h1>

            <p class="fs-6">
                <span class="fw-bold">BotaniTex</span>
                is an AI-powered textile design platform that bridges the beauty of nature with the 
                possibilities of artificial intelligence. The platform focuses on analyzing botanical 
                features, including leaf structures, vein patterns, floral shapes, textures, and natural 
                color variations, to generate distinctive, nature-inspired textile designs.
            </p>

            <p class="fs-6">
                By combining artificial intelligence with botanical image processing, 
                BotaniTex aims to transform natural elements into visually appealing, detailed, 
                and print-ready patterns optimized for cotton fabrics. Our goal is to support 
                creative textile design through intelligent automation, offering new possibilities for 
                designers and textile-related industries while celebrating the complexity and diversity of nature.
            </p>
        </div>


        <!-- Mission -->
        <div class="container mb-5 mt-5">
            <div class="row align-items-center justify-content-center">

                <div class="col-md-6">
                    <div class="row">

                        <div class="col-3">
                            <h1>Mission</h1>
                        </div>

                        <div class="col-3"></div>

                        <p>
                            Our mission is to develop an intelligent and accessible textile
                             pattern generation platform that uses AI and botanical image analysis 
                             to capture the intricate details of leaves, flowers, and other natural 
                             elements. We aim to transform these features into high-quality, visually 
                             consistent textile patterns tailored to cotton fabric printing, while 
                             exploring opportunities to improve design efficiency, preserve the uniqueness 
                             of natural forms, and encourage innovation within the textile design process.
                        </p>

                    </div>
                </div>

                <div class="col-md-6 mission-img">
                    <img
                        src="/images/mission.jpeg"
                        alt="Mission Image"
                        class="w-100 h-100 object-fit-cover"
                    />
                </div>

            </div>
        </div>


        <hr>


        <!-- Vision -->
        <div class="container mb-5 mt-5">
            <div class="row align-items-center justify-content-center">

                <div class="col-md-6 vision-img">
                    <img
                        src="/images/vision.jpeg"
                        alt="Vision Image"
                        class="w-100 h-100 object-fit-cover"
                    />
                </div>

                <div class="col-md-6">

                    <div class="row">

                        <div class="col-3">
                            <h1>Vision</h1>
                        </div>

                        <div class="col-3"></div>

                        <p>
                            To become an innovative platform for AI-driven textile design, 
                            inspiring a new generation of nature-inspired patterns through 
                            the integration of artificial intelligence, botanical analysis, 
                            and textile technology. We envision a future where natural beauty 
                            and intelligent design work together to create distinctive textile 
                            patterns that encourage creativity, enhance design possibilities, 
                            and support more thoughtful approaches to textile production.
                        </p>

                    </div>

                </div>

            </div>
        </div>

    </section>
</template>


<script>
export default {};
</script>


<style scoped>

.box {
    width: 400px;
    margin: 10px auto;
    position: relative;
    overflow: hidden;
    height: 300px;
}

.box .eye-icon {
    width: 100%;
    height: auto;
}

.content {
    color: #fff;
    background: #000;
    position: absolute;
    top: 100%;
    left: 0%;
    width: 100%;
    height: 300px;
    padding: 20px;
    box-sizing: border-box;
    transition: all 0.5s;
    align-content: center;
}

.box:hover .content {
    top: 0;
}

.vision-img {
    width: 333px;
}

</style>
```
