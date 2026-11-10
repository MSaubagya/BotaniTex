<template>
    <div>
        <SideNavBar />

        <Topnavigationbar style="top: 0;" />

        <slot />

        <button class="btn-scroll-top" type="button" aria-label="Scroll to top">
            <i class="fa-solid fa-chevron-up"></i>
        </button>

        <Footer />
    </div>
</template>

<script setup>
import { useRecaptchaProvider } from "vue-recaptcha";

useRecaptchaProvider();
</script>

<script>
import Topnavigationbar from "./partials/Topnavigationbar.vue";
import Footer from "./partials/Footer.vue";
import SideNavBar from "./partials/SideNavBar.vue";

export default {
    components: {
        Topnavigationbar,
        Footer,
        SideNavBar,
    },

    mounted() {
        $(".btn-scroll-top").on("click", function () {
            $("html, body").animate({ scrollTop: 0 }, 0);
        });

        jQuery(window).on("scroll", function () {
            if ($(window).scrollTop() >= 400) {
                $(".btn-scroll-top").addClass("show");
            } else {
                $(".btn-scroll-top").removeClass("show");
            }
        });
    },
};
</script>