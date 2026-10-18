<template>
  <section class="packs-page">
    <div class="packs-section">
      <header class="packs-heading">
        <h2>Pattern Packs</h2>
        <p>Explore collections of patterns for every occasion.</p>
      </header>

      <div class="pack-categories">
        <a
          v-for="pack in packs"
          :key="pack.name"
          :href="pack.href"
          class="pack-category"
        >
          <div class="pack-circle">
            <img :src="pack.image" :alt="pack.name" />
          </div>
          <span>{{ pack.name }}</span>
        </a>
      </div>
    </div>

    <div class="featured-section">
      <div class="featured-intro">
        <span class="intro-mark">✦</span>
        <h3>Make more with your patterns</h3>
        <p>Find a design, get inspired, and make it your own.</p>
      </div>

      <div class="pattern-cards">
        <article
          v-for="pattern in featuredPatterns"
          :key="pattern.title"
          class="pattern-card"
        >
          <img :src="pattern.image" :alt="pattern.title" />
          <p>{{ pattern.title }}</p>
        </article>
      </div>
    </div>
  </section>
</template>

<script>
export default {
  data() {
    return {
      packs: [
        {
          name: "Floral",
          image: "/images/packs/floral.jpg",
          href: "#floral",
        },
        {
          name: "Product",
          image: "/images/packs/product.jpg",
          href: "#product",
        },
        {
          name: "Abstract",
          image: "/images/packs/abstract.jpg",
          href: "#abstract",
        },
        {
          name: "Celebration",
          image: "/images/packs/celebration.jpg",
          href: "#celebration",
        },
      ],
      featuredPatterns: [
        {
          title: "Botanical print",
          image: "/images/patterns/botanical.jpg",
        },
        {
          title: "Abstract shapes",
          image: "/images/patterns/abstract.jpg",
        },
        {
          title: "Colorful checks",
          image: "/images/patterns/checks.jpg",
        },
        {
          title: "Nature inspired",
          image: "/images/patterns/nature.jpg",
        },
      ],
    };
  },
};
</script>

<style scoped>
.packs-page {
  overflow: hidden;
  color: #222126;
}

.packs-section {
  padding: 58px 24px 62px;
  background:
    radial-gradient(ellipse at 13% 70%, #f3c6d7 0, transparent 32%),
    radial-gradient(ellipse at 44% 38%, #f4e9a9 0, transparent 30%),
    radial-gradient(ellipse at 88% 78%, #f4c8bd 0, transparent 34%),
    #f3f1eb;
  text-align: center;
}

.packs-heading h2 {
  margin: 0 0 6px;
  font-size: 1.7rem;
  font-weight: 700;
}

.packs-heading p {
  margin: 0;
  color: #58565a;
}

.pack-categories {
  display: flex;
  justify-content: center;
  flex-wrap: wrap;
  gap: clamp(28px, 6vw, 76px);
  margin: 28px auto 0;
}

.pack-category {
  display: flex;
  flex-direction: column;
  align-items: center;
  gap: 10px;
  color: inherit;
  font-weight: 600;
  text-decoration: none;
}

.pack-circle {
  width: clamp(140px, 15vw, 200px);
  aspect-ratio: 1;
  padding: 9px;
  overflow: hidden;
  border: 3px solid rgb(255 255 255 / 95%);
  border-radius: 50%;
  background: white;
  box-shadow: 0 12px 26px rgb(37 34 40 / 20%);
  transition: transform 0.2s ease;
}

.pack-category:hover .pack-circle {
  transform: translateY(-4px);
}

.pack-circle img {
  width: 100%;
  height: 100%;
  border-radius: 50%;
  object-fit: cover;
}

.featured-section {
  display: grid;
  grid-template-columns: minmax(180px, 0.8fr) 3.2fr;
  align-items: center;
  gap: 28px;
  padding: 38px clamp(24px, 4vw, 64px);
  background:
    radial-gradient(ellipse at 15% 45%, #e2dce4 0, transparent 40%),
    radial-gradient(ellipse at 85% 50%, #f4ded2 0, transparent 40%),
    #efeeeb;
}

.featured-intro {
  max-width: 220px;
}

.intro-mark {
  display: grid;
  width: 54px;
  height: 54px;
  margin-bottom: 16px;
  place-items: center;
  border-radius: 16px;
  background: rgb(255 255 255 / 75%);
  color: #766783;
  font-size: 1.6rem;
  box-shadow: 0 8px 20px rgb(40 35 45 / 12%);
}

.featured-intro h3 {
  margin: 0 0 8px;
  font-size: 1.15rem;
}

.featured-intro p {
  margin: 0;
  color: #66636a;
  line-height: 1.5;
}

.pattern-cards {
  display: grid;
  grid-template-columns: repeat(4, minmax(150px, 1fr));
  gap: 14px;
}

.pattern-card {
  min-width: 0;
  padding: 8px;
  border: 1px solid rgb(255 255 255 / 90%);
  border-radius: 20px;
  background: rgb(255 255 255 / 55%);
  box-shadow: 0 8px 20px rgb(40 35 45 / 12%);
}

.pattern-card img {
  display: block;
  width: 100%;
  height: 155px;
  border-radius: 13px;
  object-fit: cover;
}

.pattern-card p {
  margin: 9px 4px 3px;
  font-size: 0.9rem;
  font-weight: 600;
}

@media (max-width: 900px) {
  .featured-section {
    grid-template-columns: 1fr;
  }

  .featured-intro {
    max-width: 420px;
  }

  .pattern-cards {
    grid-template-columns: repeat(2, minmax(150px, 1fr));
  }
}

@media (max-width: 520px) {
  .packs-section {
    padding: 42px 18px;
  }

  .pack-categories {
    gap: 22px;
  }

  .pack-circle {
    width: 125px;
  }

  .pattern-cards {
    grid-template-columns: 1fr 1fr;
    gap: 10px;
  }

  .pattern-card img {
    height: 120px;
  }
}
</style>