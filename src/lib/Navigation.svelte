<script>
    import {base} from '$app/paths';
</script>

<nav class="section-nav" aria-label="Section navigation">
    <a href="#about" aria-label="Go to About Me">  
        <img src="{base}/images/icons/profile.svg" alt="" />  
    </a>

    <a href="#tech" aria-label="Go to Technologies / Software">  
        <img src="{base}/images/icons/tech.svg" alt="" />  
    </a>

    <a href="#projects" aria-label="Go to Projects"> 
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
        transition: transform 0.2s ease;
    }

    .section-nav a:hover,
    .section-nav a:focus {
        transform: scale(1.15);
        outline: none;
    }

    @media (max-width: 500px) {
        .section-nav {
            width: 240px;
        }
    }

</style> 

