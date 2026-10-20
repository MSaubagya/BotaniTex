```vue
<template>
    <section>
        <div class="text-center mt-5 mb-5">
            <h1 class="fw-medium">FAQs</h1>
        </div>

        <div class="container faq accordion mb-5" id="accordionExample">

            <!-- FAQ 1 -->
            <div class="accordion-item rounded-3">
                <h2 class="accordion-header">
                    <button
                        class="accordion-button rounded-3 fw-semibold fs-6"
                        type="button"
                        data-bs-toggle="collapse"
                        data-bs-target="#collapseOne"
                        aria-expanded="true"
                        aria-controls="collapseOne"
                    >
                        What is BotaniTex?
                    </button>
                </h2>

                <div
                    id="collapseOne"
                    class="accordion-collapse collapse show"
                    data-bs-parent="#accordionExample"
                >
                    <hr class="my-0 mx-3" />

                    <div class="accordion-body mt-3 fs-6">
                        BotaniTex is an AI-powered textile design platform that 
                        transforms botanical elements, such as leaves and flowers, 
                        into unique, nature-inspired textile patterns..
                    </div>
                </div>
            </div>


            <!-- FAQ 2 -->
            <div class="accordion-item rounded-3 my-3">
                <h2 class="accordion-header">
                    <button
                        class="accordion-button collapsed rounded-3 fw-semibold fs-6"
                        type="button"
                        data-bs-toggle="collapse"
                        data-bs-target="#collapseTwo"
                        aria-expanded="false"
                        aria-controls="collapseTwo"
                    >
                        How does BotaniTex work?
                    </button>
                </h2>

                <div
                    id="collapseTwo"
                    class="accordion-collapse collapse"
                    data-bs-parent="#accordionExample"
                >
                    <hr class="my-0 mx-3" />

                    <div class="accordion-body mt-3 fs-6">
                        BotaniTex uses botanical image processing and AI-based techniques 
                        to analyze natural features, including leaf veins, shapes, textures, 
                        and colours, to help generate creative textile patterns.
                    </div>
                </div>
            </div>


            <!-- FAQ 3 -->
            <div class="accordion-item rounded-3 my-3">
                <h2 class="accordion-header">
                    <button
                        class="accordion-button collapsed rounded-3 fw-semibold fs-6"
                        type="button"
                        data-bs-toggle="collapse"
                        data-bs-target="#collapseThree"
                        aria-expanded="false"
                        aria-controls="collapseThree"
                    >
                        What types of images can I upload?
                    </button>
                </h2>

                <div
                    id="collapseThree"
                    class="accordion-collapse collapse"
                    data-bs-parent="#accordionExample"
                >
                    <hr class="my-0 mx-3" />

                    <div class="accordion-body mt-3 fs-6">
                        You can use botanical images such as leaves and flowers. 
                        For better results, choose clear, well-lit images with 
                        visible natural details and minimal background distractions.
                    </div>
                </div>
            </div>


            <!-- FAQ 4 -->
            <div class="accordion-item rounded-3 my-3">
                <h2 class="accordion-header">
                    <button
                        class="accordion-button collapsed rounded-3 fw-semibold fs-6"
                        type="button"
                        data-bs-toggle="collapse"
                        data-bs-target="#collapseFour"
                        aria-expanded="false"
                        aria-controls="collapseFour"
                    >
                        Can I create textile patterns from my own images?
                    </button>
                </h2>

                <div
                    id="collapseFour"
                    class="accordion-collapse collapse"
                    data-bs-parent="#accordionExample"
                >
                    <hr class="my-0 mx-3" />

                    <div class="accordion-body mt-3 fs-6">
                        BotaniTex is designed to help users transform their own 
                        botanical reference images into nature-inspired textile pattern concepts.
                    </div>
                </div>
            </div>


            <!-- FAQ 5 -->
            <div class="accordion-item rounded-3 my-3">
                <h2 class="accordion-header">
                    <button
                        class="accordion-button collapsed rounded-3 fw-semibold fs-6"
                        type="button"
                        data-bs-toggle="collapse"
                        data-bs-target="#collapseFive"
                        aria-expanded="false"
                        aria-controls="collapseFive"
                    >
                        Do I need design experience to use BotaniTex?
                    </button>
                </h2>

                <div
                    id="collapseFive"
                    class="accordion-collapse collapse"
                    data-bs-parent="#accordionExample"
                >
                    <hr class="my-0 mx-3" />

                    <div class="accordion-body mt-3 fs-6">
                        No advanced textile design experience is intended to be necessary. 
                        BotaniTex aims to make AI-assisted botanical textile design more 
                        accessible to students, designers, and creative professionals.
                    </div>
                </div>
            </div>


            <!-- FAQ 6 -->
            <div class="accordion-item rounded-3 my-3">
                <h2 class="accordion-header">
                    <button
                        class="accordion-button collapsed rounded-3 fw-semibold fs-6"
                        type="button"
                        data-bs-toggle="collapse"
                        data-bs-target="#collapseSix"
                        aria-expanded="false"
                        aria-controls="collapseSix"
                    >
                        Who can benefit from BotaniTex?
                    </button>
                </h2>

                <div
                    id="collapseSix"
                    class="accordion-collapse collapse"
                    data-bs-parent="#accordionExample"
                >
                    <hr class="my-0 mx-3" />

                    <div class="accordion-body mt-3 fs-6">
                        BotaniTex is designed for textile designers, design students, 
                        creative professionals, researchers, and anyone interested 
                        in exploring AI-generated, nature-inspired textile patterns.
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
.faq .accordion {
    --bs-accordion-active-bg: #fff;
    --bs-accordion-active-color: #000;
    --bs-accordion-btn-focus-box-shadow: none;
}

.faq .accordion-button {
    font-size: 14px;
}

.faq .accordion-button.collapsed {
    border: 1px solid gray;
}

.faq .accordion .accordion-item:has(.accordion-button:not(.collapsed)) {
    border: 1px solid #000000;
}

.faq .accordion-collapse {
    transition: all 0.3s;
}

.faq .accordion-button:not(.collapsed) {
    box-shadow: none;
}

.faq .accordion-button::after {
    background-image: url('data:image/svg+xml,<svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 448 512"><path d="M256 80c0-17.7-14.3-32-32-32s-32 14.3-32 32l0 144L48 224c-17.7 0-32 14.3-32 32s14.3 32 32 32l144 0 0 144c0 17.7 14.3 32 32 32s32-14.3 32-32l0-144 144 0c17.7 0 32-14.3 32-32s-14.3-32-32-32l-144 0 0-144z"/></svg>');
    transition-duration: 0.4s;
    font-size: 5px;
}

.faq .accordion-button:not(.collapsed)::after {
    background-image: url('data:image/svg+xml,<svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 448 512"><path d="M432 256c0 17.7-14.3 32-32 32L48 288c-17.7 0-32-14.3-32-32s14.3-32 32-32l352 0c17.7 0 32 14.3 32 32z"/></svg>');
}
</style>
```
