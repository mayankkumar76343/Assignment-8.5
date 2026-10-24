— Assignment 8.5: CSS Grid Mini-ProjectProject structure

text
Assignment-8.5/
├── index.html
├── style.css
└── README.md
1. index.html

<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <meta name="description" content="Explore a beautiful collection of photography.">
    <title>FrameSpace | Photo Gallery</title>
    <link rel="stylesheet" href="style.css">
</head>
<body>

    <header class="header">
        <a href="#" class="logo">Frame<span>Space.</span></a>

        <nav aria-label="Main navigation">
            <a href="#home">Home</a>
            <a href="#gallery">Gallery</a>
            <a href="#about">About</a>
        </nav>
    </header>

    <main id="home">
        <section class="hero">
            <p class="eyebrow">YOUR DAILY DOSE OF INSPIRATION</p>
            <h1>Discover the beauty<br>in every <span>frame.</span></h1>
            <p class="hero-text">
                A curated collection of moments, places, and stories
                captured through the lens.
            </p>
        </section>

        <section class="gallery-section" id="gallery">
            <div class="section-heading">
                <div>
                    <p class="eyebrow">THE COLLECTION</p>
                    <h2>Explore Gallery</h2>
                </div>
                <p class="gallery-count">06 PHOTOGRAPHS</p>
            </div>

            <div class="gallery-grid">
                <article class="gallery-card card-featured">
                    <img
                        src="https://images.unsplash.com/photo-1500530855697-b586d89ba3ee?auto=format&fit=crop&w=1200&q=80"
                        alt="Beautiful mountain landscape beneath an open sky"
                        loading="lazy"
                    >
                    <div class="card-info">
                        <span>01 / NATURE</span>
                        <h3>Into the Wild</h3>
                    </div>
                </article>

                <article class="gallery-card">
                    <img
                        src="https://images.unsplash.com/photo-1519608487953-e999c86e7455?auto=format&fit=crop&w=900&q=80"
                        alt="Dreamlike night sky filled with stars"
                        loading="lazy"
                    >
                    <div class="card-info">
                        <span>02 / NIGHT</span>
                        <h3>Midnight Dreams</h3>
                    </div>
                </article>

                <article class="gallery-card">
                    <img
                        src="https://images.unsplash.com/photo-1470770841072-f978cf4d019e?auto=format&fit=crop&w=900&q=80"
                        alt="Peaceful lake surrounded by green mountains"
                        loading="lazy"
                    >
                    <div class="card-info">
                        <span>03 / TRAVEL</span>
                        <h3>Quiet Escape</h3>
                    </div>
                </article>

                <article class="gallery-card">
                    <img
                        src="https://images.unsplash.com/photo-1470252649378-9c29740c9fa8?auto=format&fit=crop&w=900&q=80"
                        alt="Golden morning sunlight across a landscape"
                        loading="lazy"
                    >
                    <div class="card-info">
                        <span>04 / SUNRISE</span>
                        <h3>Golden Hour</h3>
                    </div>
                </article>

                <article class="gallery-card">
                    <img
                        src="https://images.unsplash.com/photo-1441974231531-c6227db76b6e?auto=format&fit=crop&w=900&q=80"
                        alt="Sunlight shining through a lush forest"
                        loading="lazy"
                    >
                    <div class="card-info">
                        <span>05 / FOREST</span>
                        <h3>Into the Green</h3>
                    </div>
                </article>

                <article class="gallery-card">
                    <img
                        src="https://images.unsplash.com/photo-1464822759023-fed622ff2c3b?auto=format&fit=crop&w=900&q=80"
                        alt="Majestic mountain peaks rising into the clouds"
                        loading="lazy"
                    >
                    <div class="card-info">
                        <span>06 / ADVENTURE</span>
                        <h3>Above the Clouds</h3>
                    </div>
                </article>
            </div>
        </section>

        <section class="about" id="about">
            <p class="eyebrow">OUR PHILOSOPHY</p>
            <h2>Every picture tells a story.</h2>
            <p>
                FrameSpace celebrates the extraordinary moments hidden
                in ordinary life. Explore, get inspired, and see the
                world from a different perspective.
            </p>
        </section>
    </main>

    <footer class="footer">
        <a href="#home" class="logo">Frame<span>Space.</span></a>
        <p>© 2026 FrameSpace. Created with HTML & CSS Grid.</p>
        <a href="#home">Back to top ↑</a>
    </footer>

</body>
</html>
2. style.css
This stylesheet uses CSS Grid with repeat(), minmax(), fr, named grid areas, responsive breakpoints, and overflow protection.


css

/* ---------- Global styles ---------- */

* {
    margin: 0;
    padding: 0;
    box-sizing: border-box;
}

:root {
    --background: #10110f;
    --surface: #1a1c19;
    --text: #f5f5ef;
    --muted: #a1a49b;
    --accent: #c7f36b;
    --gap: 24px;
}

html {
    scroll-behavior: smooth;
}

body {
    font-family: Arial, Helvetica, sans-serif;
    background: var(--background);
    color: var(--text);
    line-height: 1.6;
    overflow-wrap: anywhere;
}

a {
    color: inherit;
    text-decoration: none;
}

img {
    display: block;
    width: 100%;
    max-width: 100%;
    height: 100%;
    object-fit: cover;
}

/* ---------- Header: named grid areas ---------- */

.header {
    grid-area: header;
    display: grid;
    grid-template-columns: minmax(0, 1fr) auto;
    align-items: center;
    gap: var(--gap);
    padding: 24px 7%;
    border-bottom: 1px solid #30322d;
}

.logo {
    font-size: 1.5rem;
    font-weight: 800;
    letter-spacing: -1px;
}

.logo span,
.hero h1 span {
    color: var(--accent);
}

.header nav {
    display: flex;
    flex-wrap: wrap;
    gap: 28px;
}

.header nav a,
.footer > a:last-child {
    color: var(--muted);
    transition: color 0.3s ease;
}

.header nav a:hover,
.footer > a:last-child:hover {
    color: var(--accent);
}

/* ---------- Main page layout ---------- */

body {
    display: grid;
    grid-template-areas:
        "header"
        "main"
        "footer";
    grid-template-columns: minmax(0, 1fr);
    min-height: 100vh;
}

.header {
    grid-area: header;
}

main {
    grid-area: main;
    min-width: 0;
}

.footer {
    grid-area: footer;
}

/* ---------- Hero section ---------- */

.hero {
    padding: 100px 7% 85px;
    max-width: 1000px;
}

.eyebrow {
    color: var(--accent);
    font-size: 0.75rem;
    font-weight: 700;
    letter-spacing: 2px;
    margin-bottom: 16px;
}

.hero h1 {
    font-size: clamp(2.5rem, 6vw, 5rem);
    line-height: 1.08;
    letter-spacing: -3px;
    overflow-wrap: anywhere;
}

.hero-text {
    color: var(--muted);
    max-width: 500px;
    margin-top: 24px;
    font-size: 1.05rem;
}

/* ---------- Gallery section ---------- */

.gallery-section {
    padding: 30px 7% 100px;
    min-width: 0;
}

.section-heading {
    display: grid;
    grid-template-columns: minmax(0, 1fr) auto;
    align-items: end;
    gap: 16px;
    margin-bottom: 30px;
}

.section-heading .eyebrow {
    margin-bottom: 5px;
}

.section-heading h2,
.about h2 {
    font-size: clamp(1.8rem, 4vw, 2.7rem);
    line-height: 1.2;
}

.gallery-count {
    color: var(--muted);
    font-size: 0.75rem;
    letter-spacing: 1px;
}

/* Required CSS Grid: repeat(), minmax(), and fr units */

.gallery-grid {
    display: grid;
    grid-template-columns: repeat(3, minmax(0, 1fr));
    grid-template-areas:
        "featured featured card2"
        "featured featured card3"
        "card4 card5 card6";
    gap: var(--gap);
    min-width: 0;
}

.card-featured {
    grid-area: featured;
}

.gallery-card:nth-child(2) {
    grid-area: card2;
}

.gallery-card:nth-child(3) {
    grid-area: card3;
}

.gallery-card:nth-child(4) {
    grid-area: card4;
}

.gallery-card:nth-child(5) {
    grid-area: card5;
}

.gallery-card:nth-child(6) {
    grid-area: card6;
}

/* ---------- Gallery cards ---------- */

.gallery-card {
    position: relative;
    min-width: 0;
    height: 270px;
    overflow: hidden;
    border-radius: 12px;
    background: var(--surface);
    isolation: isolate;
}

.card-featured {
    height: 564px;
}

.gallery-card::after {
    content: "";
    position: absolute;
    inset: 0;
    z-index: 0;
    background: linear-gradient(
        to top,
        rgba(0, 0, 0, 0.85),
        transparent 65%
    );
    pointer-events: none;
}

.gallery-card img {
    position: absolute;
    inset: 0;
    transition: transform 0.5s ease;
}

.gallery-card:hover img {
    transform: scale(1.06);
}

.card-info {
    position: absolute;
    z-index: 1;
    left: 20px;
    right: 20px;
    bottom: 18px;
    min-width: 0;
}

.card-info span {
    color: var(--accent);
    font-size: 0.7rem;
    letter-spacing: 1.5px;
}

.card-info h3 {
    font-size: 1.2rem;
    line-height: 1.3;
    margin-top: 4px;
    overflow-wrap: anywhere;
}

/* ---------- About section ---------- */

.about {
    margin: 0 7% 90px;
    padding: 55px;
    background: var(--surface);
    border-radius: 16px;
    text-align: center;
}

.about p:last-child {
    color: var(--muted);
    max-width: 600px;
    margin: 18px auto 0;
}

/* ---------- Footer ---------- */

.footer {
    display: grid;
    grid-template-columns: repeat(3, minmax(0, 1fr));
    align-items: center;
    gap: 20px;
    padding: 30px 7%;
    border-top: 1px solid #30322d;
}

.footer p {
    color: var(--muted);
    text-align: center;
    font-size: 0.85rem;
}

.footer > a:last-child {
    justify-self: end;
    font-size: 0.9rem;
}

/* ---------- Tablet: 2 columns ---------- */

@media (max-width: 900px) {
    :root {
        --gap: 18px;
    }

    .gallery-grid {
        grid-template-columns: repeat(2, minmax(0, 1fr));
        grid-template-areas:
            "featured featured"
            "card2 card3"
            "card4 card5"
            "card6 card6";
    }

    .card-featured {
        height: 400px;
    }

    .footer {
        grid-template-columns: repeat(2, minmax(0, 1fr));
    }

    .footer p {
        grid-column: 1 / -1;
        grid-row: 2;
    }
}

/* ---------- Mobile: 1 column ---------- */

@media (max-width: 560px) {
    :root {
        --gap: 14px;
    }

    .header {
        grid-template-columns: minmax(0, 1fr);
        justify-items: center;
        padding: 20px 5%;
    }

    .header nav {
        justify-content: center;
        gap: 20px;
    }

    .hero {
        padding: 65px 5% 55px;
    }

    .hero h1 {
        letter-spacing: -1.5px;
    }

    .gallery-section {
        padding: 20px 5% 65px;
    }

    .section-heading {
        grid-template-columns: minmax(0, 1fr);
        align-items: start;
    }

    .gallery-grid {
        grid-template-columns: minmax(0, 1fr);
        grid-template-areas:
            "featured"
            "card2"
            "card3"
            "card4"
            "card5"
            "card6";
    }

    .gallery-card,
    .card-featured {
        height: 300px;
    }

    .about {
        margin: 0 5% 60px;
        padding: 35px 22px;
    }

    .footer {
        grid-template-columns: minmax(0, 1fr);
        justify-items: center;
        text-align: center;
        padding: 28px 5%;
    }

    .footer p {
        grid-column: auto;
        grid-row: auto;
    }

    .footer > a:last-child {
        justify-self: center;
    }
}

/* ---------- Reduced motion accessibility ---------- */

@media (prefers-reduced-motion: reduce) {
    html {
        scroll-behavior: auto;
    }

    *,
    *::before,
    *::after {
        transition-duration: 0.01ms !important;
        animation-duration: 0.01ms !important;
        animation-iteration-count: 1 !important;
    }
}
3. README.md

markdown

# Assignment 8.5 — CSS Grid Mini-Project

## Project Name
FrameSpace — Responsive Photo Gallery

## Description
FrameSpace is a modern, responsive photo-gallery website created
using HTML5 and CSS3. It displays a collection of photography in
an attractive grid layout with a dark theme, hover effects,
and responsive navigation.

## Features
- Responsive header and navigation
- Hero section with introductory content
- Six photography cards
- CSS Grid for the primary layout
- Named grid areas for gallery placement
- repeat(), minmax(), and fr units
- Consistent spacing using CSS variables
- Responsive layouts for desktop, tablet, and mobile
- Image overflow prevention using object-fit: cover
- Hover animations and accessibility improvements
- Footer with copyright information

## Technologies Used
- HTML5
- CSS3
- CSS Grid
- Media Queries
- Unsplash images

## Project Structure
Assignment-8.5/
├── index.html
├── style.css
└── README.md

## How to Run
1. Download or clone the project.
2. Open index.html in your browser.
3. Ensure you have an internet connection for the images.

## Responsive Testing
Test the website at these viewport widths:
- 1440px — Desktop (3-column grid)
- 768px — Tablet (2-column grid)
- 375px — Mobile (1-column grid)

## Learning Outcomes
- Understanding CSS Grid layouts
- Using named grid areas
- Creating responsive designs
- Preventing content overflow
- Applying consistent spacing and alignment

## Author
Your Name

## License
Created for educational purposes.
4. How the project meets the assignment requirements
Requirement

Implementation

Header

Logo and navigation links

Main grid layout

.gallery-grid

Multiple cards/images

Six gallery cards

Consistent gaps

gap: var(--gap)

Responsive columns

Three, two, and one column

Footer

Copyright and navigation

repeat()

repeat(3, minmax(0, 1fr))

minmax() and fr

Flexible grid columns

Named grid areas

grid-template-areas

Overflow prevention

min-width: 0, overflow-wrap, object-fit

Different screen widths

Two responsive media queries

5. Test the website
Shots: Responsive Portfolio Website Template by FrameBakers — Framer Marketplace
Desktop — 1440px

3 columns
The featured image spans two columns and two rows, with smaller gallery cards alongside it.

Lux: Responsive Portfolio Website Template by Zan Creative — Framer Marketplace
Tablet — 768px

2 columns
The featured image spans the grid width, followed by two-column rows.

Lukas: A New Picture Perfect Theme - Behance Blog - Medium
Mobile — 375px

1 column
Cards stack vertically, and the navigation and footer adapt to the smaller screen.

These are the intended responsive layouts. Open the actual project in your browser and use Developer Tools → Toggle Device Toolbar to verify them at the specified widths.

6. Upload the assignment to GitHub
Create a new repository named Assignment-8.5 on GitHub.

Add index.html, style.css, and README.md.

Commit and push the files.

Enable GitHub Pages under Settings → Pages if you want a live website.

Alternatively, run these commands from the project directory:


bash
git init
git add index.html style.css README.md
git commit -m "Complete CSS Grid mini-project"
git branch -M main
git remote add origin https://github.com/YOUR-USERNAME/Assignment-8.5.git
git push -u origin main
Replace YOUR-USERNAME with your GitHub username. The repository link will be:

https://github.com/YOUR-USERNAME/Assignment-8.5

Submission checklist


HTML file completed

CSS file completed

README added

Desktop, tablet, and mobile layouts tested

GitHub repository uploaded

Repository link submitted
The project code is ready to use, but the GitHub repository and live deployment still need to be created by you.

Next, I can help you  publish it on GitHub Pages or  prepare a submission-ready project ZIP.


This might also interest you.


Bluehost
Virtual Private Server Hosting
Blazing-fast VPS with root access, 99.9% uptime & real human support 24/7
Ad

ChatGPT is AI and can make mistakes.



No file chosenNo file chosenNo file chosen
Chat with ChatGPT
