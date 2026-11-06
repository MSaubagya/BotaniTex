<template>
    <footer class="site-footer">
        <div class="footer-content">
            <div class="company">
                <Link class="brand" :href="route('home')">BotaniTex</Link>
                <p>
                    BotaniTex harnesses AI to transform botanical elements into
                    sophisticated, print-ready textile patterns.
                </p>
            </div>

            <div class="footer-column">
                <h3>Explore</h3>
                <Link :href="route('home')">Home</Link>
                <Link :href="route('product')">Products</Link>
                <Link :href="route('make')">Makes</Link>
                <Link :href="route('model')">Models</Link>
            </div>

            <div class="footer-column">
                <h3>Company</h3>
                <Link :href="route('about-us')">About Us</Link>
                <Link :href="route('faq')">FAQ</Link>
                <Link :href="route('contact-us')">Contact Us</Link>
            </div>

            <div class="footer-column">
                <h3>Contact</h3>
                <p>123 Main Street</p>
                <p>Colombo, Sri Lanka</p>
                <a href="tel:+94700000000">+94 700 000 000</a>
                <a href="mailto:info@democompany.com">info@democompany.com</a>
            </div>
        </div>

        <div class="footer-bottom">
            © {{ new Date().getFullYear() }} BotaniTex. All rights reserved.
        </div>
    </footer>
</template>

<script>
import { Link } from "@inertiajs/inertia-vue3";

export default {
    components: {
        Link,
    },
};
</script>

<style scoped>
.site-footer {
    padding: 64px 8% 22px;
    color: #f3f5ee;
    background:
        radial-gradient(ellipse at 12% 0%, rgba(122, 151, 91, 0.2), transparent 42%),
        #18221b;
}

.footer-content {
    display: grid;
    grid-template-columns: minmax(240px, 2fr) repeat(3, minmax(130px, 1fr));
    gap: 48px;
    max-width: 1280px;
    margin: 0 auto;
}

.company {
    max-width: 340px;
}

.brand {
    display: inline-block;
    margin-bottom: 16px;
    color: #f3f5ee;
    font-size: 1.65rem;
    font-weight: 700;
    text-decoration: none;
}

.company p,
.footer-column p {
    margin: 0 0 10px;
    color: #bbc3b5;
    font-size: 0.95rem;
    line-height: 1.7;
}

.footer-column h3 {
    margin: 5px 0 18px;
    font-size: 0.95rem;
    font-weight: 600;
}

.footer-column a {
    display: block;
    width: fit-content;
    margin-bottom: 12px;
    color: #bbc3b5;
    font-size: 0.95rem;
    text-decoration: none;
    transition: color 160ms ease;
}

.footer-column a:hover {
    color: #c7dc91;
}

.footer-bottom {
    max-width: 1280px;
    margin: 42px auto 0;
    padding-top: 20px;
    border-top: 1px solid rgba(243, 245, 238, 0.16);
    color: #bbc3b5;
    font-size: 0.85rem;
    text-align: center;
}

@media (max-width: 800px) {
    .footer-content {
        grid-template-columns: repeat(2, minmax(0, 1fr));
        gap: 36px 28px;
    }
}

@media (max-width: 500px) {
    .site-footer {
        padding: 44px 7% 20px;
    }

    .footer-content {
        grid-template-columns: 1fr 1fr;
        gap: 30px 20px;
    }

    .company {
        grid-column: 1 / -1;
    }
}
</style>