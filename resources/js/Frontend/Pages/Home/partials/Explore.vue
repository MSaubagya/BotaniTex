<template>
    <main class="tools-page">
        <section class="tools-panel">
            <header class="tools-header">
                <h1>Explore every tool</h1>
                <p>Every smart action in BotaniTex. Pick one and it opens ready to run.</p>
            </header>

            <div class="toolbar">
                <nav class="categories" aria-label="Tool categories">
                    <button
                        v-for="category in categories"
                        :key="category"
                        type="button"
                        :class="{ active: selectedCategory === category }"
                        @click="selectedCategory = category"
                    >
                        {{ category }}
                    </button>
                </nav>

                <input
                    v-model="search"
                    class="search"
                    type="search"
                    placeholder="⌕  Search tools"
                    aria-label="Search tools"
                />
            </div>

            <div class="tool-list">
                <button
                    v-for="tool in filteredTools"
                    :key="tool.name"
                    type="button"
                    class="tool-chip"
                    :class="`tone-${tool.tone}`"
                    @click="$emit('select-tool', tool.name)"
                >
                    {{ tool.name }}
                </button>

                <p v-if="filteredTools.length === 0" class="empty-state">
                    No tools found.
                </p>
            </div>
        </section>
    </main>
</template>

<script>
const tools = [
    { name: "Generate pattern", category: "Image", tone: "blue" },
    { name: "Botanical motif generator", category: "Image", tone: "blue" },
    { name: "Remove background", category: "Image", tone: "yellow" },
    { name: "Change pattern colors", category: "Image", tone: "green" },
    { name: "Create seamless repeat", category: "Product", tone: "green" },
    { name: "Generate fabric mockup", category: "Product", tone: "purple" },
    { name: "Make a variation", category: "Image", tone: "blue" },
    { name: "Create a collection", category: "Product", tone: "yellow" },
    { name: "Upscale pattern", category: "Image", tone: "blue" },
    { name: "Export print-ready file", category: "Product", tone: "purple" },
];

export default {
    name: "ToolsPage",

    data() {
        return {
            categories: ["All", "Image", "Product"],
            selectedCategory: "All",
            search: "",
            tools,
        };
    },

    computed: {
        filteredTools() {
            const query = this.search.trim().toLowerCase();

            return this.tools.filter((tool) => {
                const matchesCategory =
                    this.selectedCategory === "All" ||
                    tool.category === this.selectedCategory;
                const matchesSearch = tool.name.toLowerCase().includes(query);

                return matchesCategory && matchesSearch;
            });
        },
    },
};
</script>

<style scoped>
.tools-page {
    min-height: 100vh;
    display: flex;
    justify-content: center;
    padding: 38px 24px;
    color: #25282a;
    background:
        linear-gradient(rgba(244, 245, 240, 0.48), rgba(244, 245, 240, 0.48)),
        radial-gradient(ellipse at 18% 28%, #c5d9d2 0, transparent 38%),
        radial-gradient(ellipse at 77% 22%, #d6c9d0 0, transparent 36%),
        radial-gradient(ellipse at 45% 83%, #d7d5e1 0, transparent 42%),
        #e9e7df;
}

.tools-panel {
    width: min(100%, 1120px);
    text-align: center;
}

.tools-header h1 {
    margin: 0;
    font-size: clamp(1.8rem, 3vw, 2.1rem);
    font-weight: 700;
    letter-spacing: -0.04em;
}

.tools-header p {
    margin: 8px 0 25px;
    color: #66696a;
    font-size: 0.9rem;
}

.toolbar {
    display: flex;
    justify-content: center;
    align-items: center;
    gap: 22px;
    margin-bottom: 24px;
}

.categories {
    display: flex;
    align-items: center;
    gap: 4px;
}

.categories button {
    padding: 7px 13px;
    border: 0;
    border-radius: 7px;
    background: transparent;
    color: #56595b;
    font: inherit;
    cursor: pointer;
}

.categories button.active {
    background: rgba(255, 255, 255, 0.82);
    color: #303234;
}

.search {
    width: 240px;
    padding: 8px 12px;
    border: 1px solid rgba(75, 78, 80, 0.2);
    border-radius: 7px;
    outline: none;
    background: rgba(255, 255, 255, 0.88);
    font: inherit;
    font-size: 0.85rem;
}

.search:focus {
    border-color: #8c9895;
}

.tool-list {
    display: flex;
    justify-content: center;
    align-items: center;
    flex-wrap: wrap;
    gap: 10px;
}

.tool-chip {
    padding: 5px 11px;
    border: 1px solid rgba(73, 80, 82, 0.35);
    border-radius: 4px;
    color: #303437;
    font: inherit;
    font-size: 0.8rem;
    line-height: 1.15;
    cursor: pointer;
    transition: background 150ms ease, transform 150ms ease;
}

.tool-chip:hover {
    background: rgba(255, 255, 255, 0.72);
    transform: translateY(-1px);
}

.tone-blue {
    background: rgba(176, 210, 220, 0.32);
}

.tone-yellow {
    background: rgba(239, 218, 166, 0.34);
}

.tone-green {
    background: rgba(185, 218, 183, 0.34);
}

.tone-purple {
    background: rgba(210, 190, 220, 0.34);
}

.empty-state {
    color: #66696a;
}

@media (max-width: 760px) {
    .toolbar {
        flex-direction: column;
        gap: 12px;
    }

    .categories {
        justify-content: center;
        flex-wrap: wrap;
    }

    .search {
        width: min(100%, 320px);
    }
}
</style>