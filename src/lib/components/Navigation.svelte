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

                if (rect.top <= 350 && rect.bottom >= 350) {
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
    <a href="#about" aria-label="Go to About Me" class:active={active === "about"} on:click={() => active = "about"}>
        <img src={`${base}/images/icons/profile.svg`} alt="" />
    </a>

    <a href="#tech" aria-label="Go to Technologies / Software" class:active={active === "tech"} on:click={() => active = "tech"}>
        <img src={`${base}/images/icons/tech.svg`} alt="" />
    </a>

    <a href="#projects" aria-label="Go to Projects" class:active={active === "projects"} on:click={() => active = "projects"}>
        <img src={`${base}/images/icons/projects.svg`} alt="" />
    </a>
</nav>

<style>

    .section-nav img {
        width: 32px;
        height: 32px;
        display: block;
        object-fit: contain;
        transition: transform var(--transition-fast);
    }

    .section-nav a:hover img {
        transform: scale(var(--scale-hover));
    }

    .section-nav {
        position: fixed;
        top: var(--nav-top-desktop);
        left: 50%;
        transform: translateX(-50%);
        z-index: 100;
        
        width: var(--nav-width-desktop);
        padding: 0.4rem 1rem;
        border-radius: var(--radius-pill);
        background: var(--color-primary);

        display: flex;
        justify-content: space-around;
        align-items: center;
    }

    .section-nav a {
        color: var(--color-text-muted);
        font-size: 1.8rem;
        text-decoration: none;
        line-height: 1;
        transition: transform var(--transition-fast), filter var(--transition-fast);
    }

    .section-nav a.active {
        filter: drop-shadow(0 0 6px var(--color-glow-primary));
    }

    .section-nav a.active img {
        transform: scale(var(--scale-active));
    }

    @media (max-width: 500px) {
        .section-nav {
            width: var(--nav-width-mobile);
        }
    }

</style> 

