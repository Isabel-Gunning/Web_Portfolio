<script>
    import { base } from "$app/paths";

    const profileImage = `${base}/images/pictures/Isabel_Gunning.jpg`;

    let showMore = false;

</script>

<section id="about" class="about-section">
    
    <div class="about-content">
        
        <div class="profile-card"> 
            <img src={profileImage} alt="Portrait illustration" />
        </div>

        <div class="about-text">
            <h1>About Me ...</h1>

            <p>
                Hey! My name is Isabel Gunning.
                I have a huge passion for all things art and animation and I create to build worlds that didn't exsist before. 
                
            </p>

            {#if showMore}
            <p> 
                My journey began with a childhood curiosity for design, which has since evolved into a passion for creating unique, weird and wonderful characters through art and animation. 
                Creativity is my ultimate escape and my greatest freedom. 
                My goal is simple, to translate the amazement and peace I find in the creative process into visual expierences that spark that same joy for others!
            </p>
            {/if}

            <button class="read-more-button" on:click={() => showMore = !showMore}>
                {showMore ? "Read less" : "Read more"}
            </button>

        </div>

    </div>

</section>

<style>
    .about-section {
        min-height: var(--section-min-height);
        padding: 70px var(--space-lg) var(--space-xl);
        scroll-margin-top: var(--space-section);

        display: flex;
        align-items: flex-start;
        justify-content: center;
    }

    .about-content {
        width: 100%;
        max-width: 1500px;

        display: flex;
        align-items: flex-start;
        justify-content: center;
        gap: var(--space-xl);
    }

    .profile-card {
        flex-shrink: 0;
    }

    .profile-card img {
        width: 280px;
        height: 330px;
        object-fit: cover;
        object-position: center;
        border-radius: var(--radius-lg);
    }

    .about-text {
        max-width: 500px;
        margin-top: 30px;
    }

    .about-text h1 {
        margin-bottom: var(--space-lg);
    }

    .about-text p {
        font-size: var(--font-lg);
        line-height: 1.8;
    }

    .read-more-button {
        margin-top: var(--space-md);
        padding: 0.8rem 1.4rem;

        border: none;
        border-radius: var(--radius-pill);

        background: var(--color-primary);
        color: var(--color-text-primary);

        font-family: var(--font-body);
        font-size: var(--font-base);

        cursor: pointer;

        transition: transform var(--transition-fast);
    }

    .read-more-button:hover {
        transform: scale(var(--scale-hover));
    }

    @media (max-width: 1000px) {
        .about-section {
            min-height: auto;
            padding: 
                var(--about-mobile-gap-top)
                var(--space-md)
                var(--space-xl);
            
            overflow-x: hidden;
        }

        .about-content {
            width: 100%;
            max-width: 100%;

            display: flex;
            flex-direction: column;

            align-items: center;
            justify-content: center;

            text-align: center;

            gap: var(--space-lg);
        }

        .profile-card {
            width: 100%;
            display: flex;
            justify-content: center;
        }

        .profile-card img {
            width: var(--about-image-width-mobile);
            height: var(--about-image-height-mobile);
        }

        .about-text {
            width: 100%;
            max-width: 320px;
            margin-top: 0;
        }

        .about-text h1 {
            font-size: 2.5rem;
            margin-bottom: var(--space-md);
        }

        .about-text p {
            font-size: var(--font-base);
            line-height: 1.7;
        }
    }
</style>