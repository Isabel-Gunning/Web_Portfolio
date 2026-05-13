# sv

Everything you need to build a Svelte project, powered by [`sv`](https://github.com/sveltejs/cli).

## Creating a project

If you're seeing this, you've probably already done this step. Congrats!

```bash
# create a new project in the current directory
npx sv create

# create a new project in my-app
npx sv create my-app
```

## Developing

Once you've created a project and installed dependencies with `npm install` (or `pnpm install` or `yarn`), start a development server:

```bash
npm run dev

# or start the server and open the app in a new browser tab
npm run dev -- --open
```

## Building

To create a production version of your app:

```bash
npm run build
```

You can preview the production build with `npm run preview`.

> To deploy your app, you may need to install an [adapter](https://svelte.dev/docs/kit/adapters) for your target environment.



Isabel Gunnings (C00306887) Notes on the Project

The website was designed to showcase my creative and technical work across multiple areas including art, animation, coding, 3D modelling, and crocheting.  The portfolio was inspired by scrapbook layouts, polaroids, notebooks, and other handmade design aesthetics (I went for a pastel vibe but added in the dark mode for people that may struggle to see in those range of colours). I wanted the website to feel personal, creative, interactive, and visually memorable while still remaining functional and accessible.  The site was developed using reusable Svelte components and focuses heavily on responsive design, accessibility, interaction designs, and visual consistency.

    Features - Responsive Design:

    - Mobile and desktop responsive layouts
    - Flexible CSS Grid and Flexbox layouts
    - Mobile-friendly navigation system
    - Responsive image galleries across each of the project sections it's used in
    - Scalable typography and spacing (semi manually adjusted)

    Interactive Elements:

    - Interactive navigation with active states
    - Hover animations and transitions
    - Read more toggle in About section
    - Filterable technology and project galleries
    - Scroll to top button
    - Dark mode / light mode (contrast accessibility toggle)
    - Interactive video previews (they only play when you hover over them and then reset when not being interated with)

    Accessibility Features: 

    - Semantic HTML structure
    - Keyboard accessible navigation and buttons
    - Visible keyboard focus states
    - Alt text for images
    - ARIA labels and accessibility attributes
    - Improved contrast in high contrast mode 
    - Accessible contact links

    The website was mostly made using reusable Svelte components and reusable CSS variables.

    The website was tested using keyboard navigation to ensure all major interactions could be accessed without a mouse and also a screen reader to ensure all the aria labels were working correctly. 

    I designed the website desktop first and added in the mobile view for each section as I progressed through the website development.