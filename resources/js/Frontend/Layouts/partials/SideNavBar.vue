Here’s the full `SideNavBar.vue` with the sidebar starting 18px below the top. It stays translucent until hovered or focused, then expands into a white panel.

```vue
<template>
    <aside class="side-nav" aria-label="Main navigation">
        <Link class="side-nav__brand" :href="route('home')">
            <span class="side-nav__brand-text">BotaniTex</span>
        </Link>

        <button
            class="side-nav__create"
            type="button"
            aria-label="Create"
            title="Create"
        >
            <i class="fa-solid fa-plus"></i>
            <span class="side-nav__label">Create</span>
        </button>

        <nav class="side-nav__links">
            <Link
                v-for="item in items"
                :key="item.label"
                :href="route(item.route)"
                class="side-nav__link"
                :class="{ 'is-active': item.active }"
                :aria-label="item.label"
                :title="item.label"
            >
                <i :class="item.icon"></i>
                <span class="side-nav__label">{{ item.label }}</span>
            </Link>
        </nav>
    </aside>
</template>

<script>
import { Link } from "@inertiajs/inertia-vue3";

export default {
    components: { Link },

    data() {
        return {
            items: [
                { label: "Home", route: "home", icon: "fa-solid fa-house", active: true },
                { label: "Create", route: "make", icon: "fa-solid fa-wand-magic-sparkles" },
                { label: "Projects", route: "product", icon: "fa-regular fa-folder" },
                { label: "Models", route: "model", icon: "fa-regular fa-images" },
                { label: "Pages", route: "home", icon: "fa-regular fa-window-maximize" },
                { label: "Text tools", route: "home", icon: "fa-solid fa-language" },
            ],
        };
    },
};
</script>

<style scoped>
.side-nav {
    position: fixed;
    top: 150px;
    bottom: 100px;
    left: 10px;
    z-index: 1000;
    box-sizing: border-box;
    display: flex;
    width: 50px;
    flex-direction: column;
    align-items: center;
    padding: 16px 0;
    overflow-x: hidden;
    overflow-y: auto;
    border: 1px solid transparent;
    border-radius: 14px 14px 14px 14px;
    background: rgba(255, 255, 255, 0.22);
    backdrop-filter: blur(12px);
    -webkit-backdrop-filter: blur(12px);
    transition:
        width 200ms ease,
        background-color 200ms ease,
        box-shadow 200ms ease;
}

.side-nav:hover,
.side-nav:focus-within {
    width: 220px;
    align-items: stretch;
    padding-right: 12px;
    padding-left: 12px;
    border-color: rgba(0, 0, 0, 0.06);
    background: rgba(255, 255, 255, 0.97);
    box-shadow: 0 5px 24px rgba(0, 0, 0, 0.12);
}

.side-nav__brand {
    display: flex;
    height: 28px;
    flex: 0 0 auto;
    align-items: center;
    justify-content: center;
    margin: 2px 0 23px;
    color: #171717;
    font-size: 17px;
    font-weight: 700;
    letter-spacing: -0.7px;
    text-decoration: none;
    white-space: nowrap;
}

.side-nav__create,
.side-nav__link {
    box-sizing: border-box;
    display: flex;
    width: 100%;
    min-width: 0;
    height: 40px;
    flex: 0 0 auto;
    align-items: center;
    justify-content: center;
    gap: 14px;
    padding: 0;
    border: 0;
    border-radius: 10px;
    background: transparent;
    color: #202020;
    font: inherit;
    font-size: 15px;
    text-decoration: none;
    white-space: nowrap;
    cursor: pointer;
    transition: background-color 140ms ease;
}

.side-nav__create {
    margin-bottom: 16px;
}

.side-nav__links {
    display: flex;
    flex-direction: column;
    gap: 8px;
}

.side-nav__create i,
.side-nav__link i {
    width: 40px;
    flex: 0 0 40px;
    text-align: center;
}

.side-nav__label,
.side-nav__brand-text {
    display: none;
    opacity: 0;
}

.side-nav:hover .side-nav__label,
.side-nav:focus-within .side-nav__label,
.side-nav:hover .side-nav__brand-text,
.side-nav:focus-within .side-nav__brand-text {
    display: inline;
    opacity: 1;
}

.side-nav:hover .side-nav__brand,
.side-nav:focus-within .side-nav__brand {
    justify-content: flex-start;
    padding-left: 10px;
}

.side-nav:hover .side-nav__create,
.side-nav:focus-within .side-nav__create,
.side-nav:hover .side-nav__link,
.side-nav:focus-within .side-nav__link {
    justify-content: flex-start;
    padding: 0 8px;
}

.side-nav__link:hover,
.side-nav__create:hover {
    background: #f0f0f0;
}

.side-nav__link.is-active {
    background: rgba(220, 220, 220, 0.78);
}

@media (prefers-reduced-motion: reduce) {
    .side-nav {
        transition: none;
    }
}
</style>
```