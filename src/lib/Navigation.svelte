<script>
    import { base } from '$app/paths';
    import { onMount } from 'svelte';

    let active = "about";

    onMount(() => {
        const handleScroll = () => {
            const sections = ["about", "tech", "projects"];

            for (let id of sections) {
                const el = document.getElementById(id);
                if (!el) continue;

                const rect = el.getBoundingClientRect();

                if (rect.top <= 200 && rect.bottom >= 200) {
                    active = id;
                }
            }
        };

        window.addEventListener("scroll", handleScroll);
        handleScroll();

        return () => {
            window.removeEventListener("scroll", handleScroll);
        };
    });
</script>

<nav class="section-nav" aria-label="Section navigation">
    <a href="#about" aria-label="Go to About Me" class:active={active === "about"}>
        <img src="{base}/images/icons/profile.svg" alt="" />
    </a>

    <a href="#tech" aria-label="Go to Technologies / Software" class:active={active === "tech"}>
        <img src="{base}/images/icons/tech.svg" alt="" />
    </a>

    <a href="#projects" aria-label="Go to Projects" class:active={active === "projects"}>
        <img src="{base}/images/icons/projects.svg" alt="" />
    </a>
</nav>

<style>

    .section-nav img {
        width: 32px;
        height: 32px;
        display: block;
        transition: transform 0.2s ease;
    }

    .section-nav a:hover img {
        transform: scale(1.15);
    }

    .section-nav {
        position: fixed;
        top: 225px;
        left: 50%;
        transform: translateX(-50%);
        z-index: 100;
        
        width: 320px;
        padding: 0.4rem 1rem;
        border-radius: 999px;
        background: #f9e983;

        display: flex;
        justify-content: space-around;
        align-items: center;
    }

    .section-nav a {
        color: #a89b86;
        font-size: 1.8rem;
        text-decoration: none;
        line-height: 1;
        transition: transform 0.2s ease, filter 0.2s ease;
    }

    .section-nav a.active {
        filter: drop-shadow(0 0 6px rgba(249, 233, 131, 0.9));
    }

    .section-nav a.active img {
        transform: scale(1.25);
    }

    @media (max-width: 500px) {
        .section-nav {
            width: 240px;
        }
    }

</style> 

