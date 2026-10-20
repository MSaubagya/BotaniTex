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

        
    <section class="focus-section py-5">
        <div class="container">
            <div class="text-center mb-5">
                <h2 class="focus-heading">Our Key Focus Areas</h2>
                <p class="focus-subtitle">
                    Combining nature, artificial intelligence, and textile innovation.
                </p>
            </div>

            <div class="row g-4">
                <div class="col-md-6 col-lg-3">
                    <div class="focus-card">
                        <div class="focus-icon">✦</div>
                        <h4>AI-Powered Design</h4>
                        <p>
                            Generate distinctive botanical textile patterns
                            using artificial intelligence.
                        </p>
                    </div>
                </div>

                <div class="col-md-6 col-lg-3">
                    <div class="focus-card">
                        <div class="focus-icon">❧</div>
                        <h4>Botanical Analysis</h4>
                        <p>
                            Analyze leaf veins, floral shapes, textures,
                            and natural colour variations.
                        </p>
                    </div>
                </div>

                <div class="col-md-6 col-lg-3">
                    <div class="focus-card">
                        <div class="focus-icon">✿</div>
                        <h4>Pattern Innovation</h4>
                        <p>
                            Transform natural details into creative,
                            repeatable textile patterns.
                        </p>
                    </div>
                </div>

                <div class="col-md-6 col-lg-3">
                    <div class="focus-card">
                        <div class="focus-icon">▧</div>
                        <h4>Cotton Print Optimization</h4>
                        <p>
                            Focus on pattern clarity and suitability
                            for cotton fabric printing.
                        </p>
                    </div>
                </div>
            </div>
        </div>
    </section>



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


.focus-section {
    background-color: #E8DFCC;
}

.focus-heading {
    color: #243A2B;
    font-size: clamp(28px, 4vw, 40px);
    font-weight: 700;
}

.focus-subtitle {
    color: #5F6259;
    max-width: 600px;
    margin: 12px auto 0;
}

.focus-card {
    height: 100%;
    padding: 28px 22px;
    background: #FFFFFF;
    border-radius: 14px;
    text-align: center;
    border-bottom: 3px solid #B08A4A;
    transition: transform 0.25s ease,
                box-shadow 0.25s ease;
}

.focus-card:hover {
    transform: translateY(-6px);
    box-shadow: 0 12px 28px rgba(36, 58, 43, 0.12);
}

.focus-icon {
    font-size: 38px;
    color: #B08A4A;
    margin-bottom: 15px;
}

.focus-card h4 {
    color: #243A2B;
    font-size: 18px;
    font-weight: 600;
    margin-bottom: 12px;
}

.focus-card p {
    color: #62665E;
    font-size: 14px;
    line-height: 1.7;
    margin-bottom: 0;
}


</style>
```
