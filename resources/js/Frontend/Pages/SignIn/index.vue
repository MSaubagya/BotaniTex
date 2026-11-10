<template>
    <AppLayout> 
        <BannerSection/>
        <Signup/>
    </AppLayout>
</template>

<script>
import AppLayout from "@@/Layouts/AppLayout.vue";
import SignIn from "./partials/SignIn.vue";
import Signup from "./partials/Signup.vue";
export default {
    components: {
        AppLayout,
        SignIn,
        Signup,
    },
};
</script>

<style></style>
