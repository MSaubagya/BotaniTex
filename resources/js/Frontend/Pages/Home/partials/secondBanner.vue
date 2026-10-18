<template>
    <section class="social-section">
        <div class="social-content">
            <header class="section-heading">
                <h2>Create social content</h2>
                <p>Size it, restyle it, and polish it for every feed.</p>
            </header>

            <div class="social-cards">
                <article
                    v-for="item in socialTools"
                    :key="item.title"
                    class="social-card"
                >
                    <div class="image-wrap">
                        <img :src="item.image" :alt="item.title" />
                        <span class="platform-icon" :class="item.platform">
                            {{ item.icon }}
                        </span>
                    </div>
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
            socialTools: [
                {
                    title: "Create a professional portrait",
                    image: "/images/Bikes/Banner-images/brand-17.jpg",
                    platform: "instagram",
                    icon: "◎",
                },
                {
                    title: "Change model expression",
                    image: "/images/Bikes/Banner-images/brand-12.jpg",
                    platform: "facebook",
                    icon: "f",
                },
                {
                    title: "Change outfit",
                    image: "/images/Bikes/Banner-images/brand-13.jpg",
                    platform: "linkedin",
                    icon: "in",
                },
                {
                    title: "Create a story",
                    image: "/images/Bikes/Banner-images/brand-14.jpg",
                    platform: "tiktok",
                    icon: "♪",
                },
                {
                    title: "Replace background",
                    image: "/images/Bikes/Banner-images/brand-15.jpg",
                    platform: "instagram",
                    icon: "◎",
                },
                {
                    title: "Change aspect ratio",
                    image: "/images/Bikes/Banner-images/brand-16.jpg",
                    platform: "instagram",
                    icon: "◎",
                },
            ],
        };
    },
};
</script>

<style scoped>
.social-section {
    padding: 44px 0;
    overflow: hidden;
    background:
        radial-gradient(ellipse at 15% 50%, #f4e9e4 0, transparent 52%),
        radial-gradient(ellipse at 80% 40%, #eee8f0 0, transparent 48%),
        #f0eeeb;
}

.social-content {
    padding-left: clamp(22px, 8.5vw, 165px);
}

.section-heading {
    margin-bottom: 28px;
}

.section-heading h2 {
    margin: 0 0 5px;
    font-size: 1.05rem;
    font-weight: 700;
}

.section-heading p {
    margin: 0;
    color: #666;
    font-size: 0.9rem;
}

.social-cards {
    display: flex;
    gap: 14px;
    overflow-x: auto;
    padding: 4px 24px 12px 0;
    scrollbar-width: none;
}

.social-cards::-webkit-scrollbar {
    display: none;
}

.social-card {
    flex: 0 0 290px;
    padding: 8px;
    border: 1px solid rgb(255 255 255 / 90%);
    border-radius: 21px;
    background: rgb(255 255 255 / 60%);
    box-shadow: 0 8px 20px rgb(35 35 35 / 12%);
}

.image-wrap {
    position: relative;
    height: 120px;
}

.image-wrap img {
    width: 100%;
    height: 100%;
    border-radius: 13px;
    object-fit: cover;
}

.platform-icon {
    position: absolute;
    top: 4px;
    right: 4px;
    display: grid;
    width: 26px;
    height: 26px;
    place-items: center;
    border-radius: 8px;
    background: white;
    font-weight: 700;
}

.instagram {
    color: #e130a2;
}

.facebook {
    color: #1877f2;
    font-size: 1.2rem;
}

.linkedin {
    color: #0a66c2;
    font-size: 0.9rem;
}

.tiktok {
    color: #111;
    font-size: 1.2rem;
}

.social-card > p {
    margin: 9px 4px 3px;
    font-size: 0.88rem;
    font-weight: 600;
}
</style>