<script> 
    
    import {base} from "$app/paths";
    
    let activeFilter = "art";

    const filters = ["art", "design","coding"];

    const tools = [

    //Art Software 
    {name:"Photoshop", category:"art", icon:`${base}/images/icons/photoshop.svg`},
    {name:"Illustrator", category:"art", icon:`${base}/images/icons/illustrator.svg`},
    {name:"Animator", category:"art", icon:`${base}/images/icons/animator.svg`},
    {name:"After Effects", category:"art", icon:`${base}/images/icons/aftereffects.svg`},
    {name:"Premiere Pro", category:"art", icon:`${base}/images/icons/premierepro.svg`},
    {name:"Inkscape", category:"art", icon:`${base}/images/icons/inkscape.svg`},
    {name:"Ibis Paint", category:"art", icon:`${base}/images/icons/ibispaint.png`},
    {name:"Krita", category:"art", icon:`${base}/images/icons/krita.svg`},
    {name:"Aseprite", category:"art", icon:`${base}/images/icons/aseprite.svg`},
    {name:"Autodesk Maya", category:"art", icon:`${base}/images/icons/autodeskmaya.jpg`},

    // Design Software
    {name:"Figma", category:"design", icon:`${base}/images/icons/figma.svg`},
    {name:"Penpot", category:"design", icon:`${base}/images/icons/penpot.svg`},
    {name:"Canva", category:"design", icon:`${base}/images/icons/canva.svg`},
    {name:"FontStruct", category:"design", icon:`${base}/images/icons/fontstruct.jpg`},

    // Coding Languages & Software
    {name:"HTML5", category:"coding", icon:`${base}/images/icons/html5.svg`},
    {name:"CSS", category:"coding", icon:`${base}/images/icons/css.svg`},
    {name:"JavaScript", category:"coding", icon:`${base}/images/icons/js.svg`},
    {name:"C++", category:"coding", icon:`${base}/images/icons/cpp.svg`},
    {name:"Svelte", category:"coding", icon:`${base}/images/icons/svelte.svg`},
    {name:"GitHub", category:"coding", icon:`${base}/images/icons/github.svg`},
    {name:"Codeberg", category:"coding", icon:`${base}/images/icons/codeberg.svg`},
    {name:"VS Code", category:"coding", icon:`${base}/images/icons/vscode.svg`},
    {name:"Visual Studio", category:"coding", icon:`${base}/images/icons/visualstudio.svg`}

    ];

    $: filteredTools = tools.filter(
        (tool) => tool.category === activeFilter
    );
</script>


<section id="tech" class="tech-section">

    <div class="tech-content">
        <h1>Technologies / Software</h1>

        <p>
            A collection of creative and technical tools I have explored through art, design and coding!
        </p>

        <div class ="filter-nav">

            {#each filters as filter (filter)}

            <button
                class:active={activeFilter === filter}
                on:click={() => activeFilter = filter}
            >
                {filter}
            </button>
        {/each}
    </div>

    <div class="tool-grid">
            {#each filteredTools as tool (tool.name)}
                
                <article class="tool-note">

                    <span class="pin"></span>

                    <img src={tool.icon} alt={tool.name} />

                    <h2>{tool.name}</h2>

                </article>
            {/each}
        </div>
    </div>

</section>

<style>
    .tech-section {
        min-height: var(--section-min-height);
        padding: var(--space-xl);
        scroll-margin-top: var(--space-section);

        display: flex;
        align-items: center;
        justify-content: center;
    }

    .tech-content {
        width: 100%;
        max-width: 1100px;
        text-align: center;
    }

    .tech-content h1 {
        margin-bottom: var(--space-md);
    }

    .tech-content p {
        font-size: var(--font-lg);
        margin-bottom: var(--space-lg);
    }

    .filter-nav {
        width:fit-content;
        margin: 
        var(--space-lg)
        auto
        var(--space-xl);

        padding: 0.35rem;
        display: flex;
        gap: 0.25rem;
        border-radius: var(--radius-pill);
        background: rgba(244, 238, 255, 0.85);
        backdrop-filter: blur(8px);
    }

    .filter-nav button {
        padding: 0.75rem 1.4rem;
        border: none;
        border-radius: var(--radius-pill);
        background: transparent;
        color: var(--color-text-muted);
        font-family: var(--font-body);
        font-size: var(--font-base);
        text-transform: capitalize;
        cursor: pointer;
        transition: 
            background-color var(--transition-fast),
            transform var(--transition-fast);
    }

    .filter-nav button.active {
        background: #d8c2ff;
        color: #55311b;
    }

    .filter-nav button:hover {
        transform: translateY(-2px);
    }

    .tool-grid {
        min-height: 430px;
        display: grid;
        grid-template-columns:
            repeat(auto-fit, minmax(170px, 1fr));
        
        align-content: start;
        gap: var(--space-lg);
        transition: all 0.25s ease;
    }

    .tool-note {
        position: relative;
        min-height: 190px;
        padding: 
            2.5rem
            1rem
            1.5rem;

        background: #e9ddff;
        border-radius: 8px;
        display: flex;
        flex-direction: column;
        align-items: center;
        justify-content: center;
        box-shadow: 
            8px
            10px
            0
            rgba(85, 49, 27, 0.12);

        transform: rotate(-1.5deg);
        transition: transform var(--transition-fast);
    }

    .tool-note:nth-child(even) {
        transform: rotate(1.5deg);
    
    }

    .tool-note:hover {
        transform: rotate(0deg) scale(1.04);
    }

    .pin {
        position: absolute;
        top: 12px;
        left: 50%;
        transform: translateX(-50%);
        width: 22px;
        height: 22px;
        background: #9f7aea;
        border-radius: 50%;
        box-shadow: 
            0
            3px
            0
            rgba(85, 49, 27, 0.25);
    }

    .tool-note img {
        width: 64px;
        height: 64px;
        object-fit: contain;
        margin-bottom: var(--space-md);
    }

    .tool-note h2 {
        margin: 0;
        font-size: var(--font-lg);
    }

    @media (max-width: 800px) {

        .tech-section {
            padding:
                var(--space-xl)
                var(--space-md);
        }

        .filter-nav {
            width: 100%;
            max-width: 340px;
        }

        .filter-nav button {
            flex: 1;

            padding: 
                0.7rem
                0.8rem;
        }

        .tool-grid {
            min-height: 520px;
            grid-template-columns: repeat(2, 1fr);
            gap: var(--space-md);
        }

        .tool-note {
            min-height: 160px;
        }
    }
</style>