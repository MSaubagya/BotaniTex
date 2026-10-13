<template>
    <section class="showcase">
        <!-- Horizontal brand strip -->
        <div class="brand-strip">
            <div class="brand-track">
                <div v-for="brand in brands" :key="brand.name" class="brand-card">
                    <img :src="brand.image" :alt="brand.name" />
                </div>
            </div>
        </div>

        <!-- Featured cards -->
        <div class="featured">
            <h2>Explore our patterns</h2>

            <div class="card-row">
                <article
                    v-for="(item, index) in patterns"
                    :key="item.title"
                    class="pattern-card"
                >
                    <img :src="item.image" :alt="item.title" />
                    <span class="card-number">
                        {{ String(index + 1).padStart(2, "0") }}
                    </span>
                    <p>{{ item.title }}</p>
                </article>
            </div>
        </div>
    </section>
</template>

<script>
export default {
    data() {
        return {
            brands: [
                { name: "Brand One", image: "/images/Bikes/Banner-images/brand-1.jpg" },
                { name: "Brand Two", image: "/images/Bikes/Banner-images/brand-2.jpg" },
                { name: "Brand Three", image: "/images/Bikes/Banner-images/brand-3.jpg" },
                { name: "Brand Four", image: "/images/Bikes/Banner-images/brand-4.jpg" },
                { name: "Brand Five", image: "/images/Bikes/Banner-images/brand-5.jpg" },
                { name: "Brand Six", image: "/images/Bikes/Banner-images/brand-6.jpg" },
            ],
            patterns: [
                { title: "Floral pattern", image: "/images/Bikes/Banner-images/brand-7.jpg" },
                { title: "Desert pattern", image: "/images/Bikes/Banner-images/brand-8.jpg" },
                { title: "Graphic pattern", image: "/images/Bikes/Banner-images/brand-9.jpg" },
                { title: "Minimal pattern", image: "/images/Bikes/Banner-images/brand-10.jpg" },
                { title: "Nature pattern", image: "/images/Bikes/Banner-images/brand-11.jpg" },
            ],
        };
    },
};
</script>

<style scoped>
.showcase {
    overflow: hidden;
    color: #202124;
    background:
        radial-gradient(ellipse at 20% 45%, #c1d7d1 0, transparent 42%),
        radial-gradient(ellipse at 80% 65%, #d9c9df 0, transparent 42%),
        #e9e5df;
}

.brand-strip {
    overflow-x: auto;
    padding: 12px 20px;
    border-bottom: 1px solid rgb(255 255 255 / 65%);
}

.brand-track {
    display: flex;
    width: max-content;
    gap: 12px;
}

.brand-card {
    display: grid;
    width: 150px;
    height: 120px;
    place-items: center;
    overflow: hidden;
    border: 1px solid rgb(255 255 255 / 80%);
    border-radius: 14px;
    background: rgb(255 255 255 / 72%);
}

.brand-card img {
    width: 100%;
    height: 100%;
    object-fit: contain;
}

.featured {
    padding: 36px clamp(20px, 4vw, 56px) 52px;
}

.featured h2 {
    margin: 0 0 20px;
    font-size: clamp(1.35rem, 2vw, 1.8rem);
}

.card-row {
    display: grid;
    grid-template-columns: repeat(5, minmax(200px, 1fr));
    gap: 18px;
}

.pattern-card {
    position: relative;
    min-width: 0;
    padding: 8px;
    overflow: hidden;
    border: 1px solid rgb(255 255 255 / 90%);
    border-radius: 22px;
    background: rgb(255 255 255 / 62%);
    box-shadow: 0 10px 28px rgb(40 40 40 / 14%);
}

.pattern-card img {
    display: block;
    width: 100%;
    height: 170px;
    border-radius: 15px;
    object-fit: cover;
}

.pattern-card p {
    margin: 10px 4px 4px;
    font-weight: 600;
}

.card-number {
    position: absolute;
    top: 95px;
    left: 12px;
    color: white;
    font-size: 3.5rem;
    font-weight: 700;
    line-height: 1;
    text-shadow: 0 2px 8px rgb(0 0 0 / 30%);
}

@media (max-width: 900px) {
    .card-row {
        grid-template-columns: repeat(2, minmax(200px, 1fr));
    }
}

@media (max-width: 520px) {
    .card-row {
        grid-template-columns: 1fr;
    }

    .pattern-card img {
        height: 210px;
    }
}
</style>