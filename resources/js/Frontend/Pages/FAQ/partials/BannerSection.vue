```vue
<template>
    <section>
        <div class="hero">
        </div>
    </section>
</template>

<script>
export default {
    components: {},
};
</script>

<style scoped>
.hero {
    background: url("images/faq.jpeg")
        no-repeat center center;
    justify-content: center;
    background-size: cover;
    flex-direction: column;
    align-items: center;
    display: flex;
    height: 50vh;
    width: 100%;
}

.down {
    text-align: center;
    position: absolute;
    opacity: 0.6;
    height: 40px;
    width: 100%;
    bottom: 0;
}

.form-control:focus {
    border-color: #000;
    box-shadow: none;
}
</style>
```
