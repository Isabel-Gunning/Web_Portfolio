<script>
    import { base } from "$app/paths";
    import { onMount } from "svelte";

    let active = "about";

    const links = [
        {
            id: "about",
            label: "About",
            icon: `${base}/images/icons/profile.svg`
        },
        {
            id: "tech",
            label: "Tech",
            icon: `${base}/images/icons/tech.svg`
        },
        {
            id: "projects",
            label: "Projects",
            icon: `${base}/images/icons/projects.svg`
        },
        {
            id: "qa",
            label: "Q&A",
            icon: `${base}/images/icons/questions.svg`
        },
        {
            id: "contact",
            label: "Contact",
            icon: `${base}/images/icons/contact.svg`
        }
    ];

    onMount(() => {
        const handleScroll = () => {
            for (const link of links) {
                const el = document.getElementById(link.id);
                
                if (!el) continue;

                const rect = el.getBoundingClientRect();

                if (rect.top <= 350 && rect.bottom >= 350) {
                    active = link.id;
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
    {#each links as link (link.id)}
        <a
            href={`#${link.id}`}
            class:active={active === link.id}
            on:click={() => active = link.id}
        >
            <img src={link.icon} alt="" />
            <span>{link.label}</span>
        </a>
    {/each}
</nav>

<style>
    .section-nav {
        position: sticky;
        top: 12px;
        z-index: 100;

        margin: 0 auto;

        width: 520px;
        padding: 0.35rem;

        border-radius: var(--radius-pill);
        background: rgba(255, 255, 255, 0.85);

        display: flex;
        align-items: center;
        justify-content: space-between;

        box-shadow: 0 8px 24px rgba(0, 0, 0, 0.08);
        backdrop-filter: blur(8px);
    }

    .section-nav a {
        flex: 1;

        padding: 0.8rem 1rem;
        border-radius: var(--radius-pill);

        display: flex;
        align-items: center;
        justify-content: center;
        gap: 0.5rem;

        color: var(--color-text-muted);
        text-decoration: none;
        font-size: var(--font-base);

        transition:
            background-color var(--transition-fast),
            color var(--transition-fast),
            transform var(--transition-fast);
    }

    .section-nav img {
        width: 26px;
        height: 26px;
        object-fit: contain;
        opacity: 0.65;
    }

    .section-nav a:hover {
        transform: translateY(-2px);
    }

    .section-nav a.active {
        background: var(--color-primary);
        color: var(--color-text-primary);
        box-shadow: 0 4px 14px rgba(0, 0, 0, 0.08);
    }

    .section-nav a.active img {
        opacity: 1;
    }

    @media (max-width: 650px) {
        .section-nav {
            width: 90%;
            padding: 0.4rem;
        }

        .section-nav a {
            padding: 0.7rem 0.4rem;
            gap: 0;
        }

        .section-nav a span {
            display: none;
        }

        .section-nav img {
            width: 24px;
            height: 24px;
        }
    }
</style>