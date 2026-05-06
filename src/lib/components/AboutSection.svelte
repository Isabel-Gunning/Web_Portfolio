<script>

    import {base} from "$app/paths";

    const images = [
        `${base}/images/pictures/profile-image.png`,
        `${base}/images/pictures/Isabel_Gunning.jpg`
    ];

    let currentImage = 0;
    
    function previousImage() {
        currentImage = currentImage === 0 ? images.length - 1 : currentImage - 1;
    }

    function nextImage() {
        currentImage = currentImage === images.length - 1 ? 0 : currentImage + 1;
    }
    
</script>

<section id = "about" class="about-section">
    
    <div class="about-content">
        
        <div class="profile-card"> 
            <img src= {images[currentImage]} alt="Portrait illustration" />
        
            <div class="image-controls">
                <button on:click={previousImage} aria-label="Previous image">
                    <img src={`${base}/images/icons/arrow-left.svg`} alt="" />
                </button>


                <button on:click={nextImage} aria-label="Next image">
                    <img src={`${base}/images/icons/arrow-right.svg`} alt="" />
                </button>
            </div>
        </div>

        <div class ="about-text">
            <h1> About Me ... </h1>

            <p>
                About me will go here!
            </p>

            <p> 
                Describe my interests, creative style, programming experience, and goals.
            </p>
        </div>

    </div>

</section>

<style>
    .about-section {
        min-height: var(--section-min-height);
        padding: var(--space-lg);
        scroll-margin-top: var(--space-section);

        display: flex;
        align-items: center;
        justify-content: center;
    }

    .about-content {
        width: 100%;
        max-width: 1100px;

        display: flex;
        align-items: center;
        justify-content: center;
        gap: var(--space-xl);
    }

    .profile-card img {
        width: 220px;
        height: 280px;
        object-fit: cover;
        object-position: center;
        border-radius: var(--radius-lg);
    }

    .profile-card {
        flex-shrink: 0;
    }

    .image-controls {
        display: flex;
        justify-content: center;
        gap: var(--space-md);
        margin-top: var(--space-md);
    }

    .image-controls button {
        width: 52px;
        height: 44px;
        border-radius: var(--radius-pill);

        background: var(--color-primary);
        color: var(--color-text-muted);
        
        font-size: var(--font-lg);

        transition: transform var(--transition-fast);
    }

    .image-controls button:hover {
        transform: scale(var(--scale-hover));
    }

    .image-controls button img {
        width: 36px;
        height: 36px;

        object-fit: contain;
    }

    .about-text {
        max-width: 500px;
        margin-top: -30px;
    }

    .about-text h1 {
        margin-bottom: var(--space-lg);
    }

    .about-text p {
        font-size: var(--font-lg);
        line-height: 1.8;
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
            flex-direction: column;
            align-items: center;
        }

        .profile-card img {
            width: var(--about-image-width-mobile);
            height: var(--about-image-height-mobile);
        }

        .image-controls {
            margin-top: var(--space-md);
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