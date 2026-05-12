<script>

    import {base} from "$app/paths";

    function scrollToTop() {
        window.scrollTo({
            top: 0,
            behavior: "smooth"
        });
    }
</script>

<button class="scroll-top" on:click={scrollToTop}>
    <img src={`${base}/images/icons/arrow-up.svg`} alt="" />
</button>

<style>
    .scroll-top {
    position: fixed;
    bottom: 24px;
    right: 24px;
    width: 56px;
    height: 42px;
    border-radius: var(--radius-pill);
    background: var(--floating-button-background);
    backdrop-filter: blur(6px);
    border: none;
    cursor: pointer;
    color: var(--color-text-muted);
    font-size: 1.4rem;
    font-weight: bold;
    display: flex;
    align-items: center;
    justify-content: center;
    z-index: 999;
    box-shadow: 0 4px 12px var(--floating-button-shadow);
    transition:
        transform var(--transition-fast),
        background-color var(--transition-fast),
        opacity var(--transition-fast);
    }

    .scroll-top:hover {
        transform: scale(var(--scale-hover));
        background: var(--floating-button-background-hover);
    }

    .scroll-top img {
        width: 28px;
        height: 28px;
        object-fit: contain;
    }

    @media (max-width: 800px) {

        .scroll-top {
            width: 50px;
            height: 38px;
            bottom: 18px;
            right: 18px;

            font-size: 1.2rem;
        }
    }
</style>