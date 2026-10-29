1. HTML Code (index.html)
HTML
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>The Art of Timeless Digital Typography | Editorial</title>
    <link rel="stylesheet" href="style.css">
    <link href="https://fonts.googleapis.com/css2?family=Inter:wght@300;400;500;600&family=Playfair+Display:ital,wght@0,600;0,700;1,400&display=swap" rel="stylesheet">
</head>
<body>

    <!-- Main Content Container with Optimal Line Length Max-Width -->
    <main class="article-container">
        
        <!-- Article Header -->
        <header class="article-header">
            <span class="category">Design Philosophy</span>
            <h1>The Art of Timeless Digital Typography</h1>
            <p class="subtitle">How modern CSS functions like <code>clamp()</code> and fluid units bridge the gap between traditional print design and flexible screen viewports.</p>
            <div class="meta-info">
                <img src="https://images.unsplash.com/photo-1534528741775-53994a69daeb?w=100&auto=format&fit=crop&q=80" alt="Author Avatar" class="author-avatar">
                <div>
                    <span class="author-name">Elena Rostova</span>
                    <span class="publish-date">Published on October 24, 2026 &bull; 5 min read</span>
                </div>
            </div>
        </header>

        <!-- Featured Responsive Image -->
        <div class="image-wrapper">
            <img src="https://images.unsplash.com/photo-1507238691740-187a5b1d37b8?auto=format&fit=crop&w=1200&q=80" alt="Minimalist workspace setup with typographic prints">
            <figcaption>Clean grid layouts and robust scale factors elevate digital storytelling.</figcaption>
        </div>

        <!-- Article Body Content -->
        <div class="article-body">
            <p class="lead">Typography is the foundation of digital user experience. When text scales gracefully across mobile devices, tablets, and ultra-wide desktop monitors, readability increases, and the design feels remarkably cohesive.</p>
            
            <h2>The Shift Toward Fluid Sizing</h2>
            <p>For years, developers relied on complex media query breakpoints to jump font sizes up and down. While breakpoints remain essential for layout structures, typography can now be handled dynamically using CSS math functions like <code>clamp()</code>.</p>
            
            <p>By defining a minimum size, a fluid preferred size (using viewport widths), and a maximum size, text smoothly adapts without sudden visual jumps. This creates a more polished reading experience regardless of the device screen size.</p>

            <!-- Secondary Image Example -->
            <div class="image-wrapper">
                <img src="https://images.unsplash.com/photo-1517841905240-472988babdf9?auto=format&fit=crop&w=1200&q=80" alt="Person reviewing design wireframes on a tablet">
                <figcaption>Testing contrast, hierarchy, and scaling across varying form factors.</figcaption>
            </div>

            <h2>Best Practices for Image Integrity</h2>
            <p>Responsive images are just as vital as fluid text. Without proper constraints, large images can blow out container bounds and create unwanted horizontal scrolling.</p>
            
            <p>Applying <code>max-width: 100%</code> alongside <code>height: auto</code> ensures that media scales down proportionally inside narrow mobile viewports while never exceeding its native resolution on large desktop screens.</p>
        </div>

        <!-- Article Footer / Author Bio -->
        <footer class="article-footer">
            <div class="tags">
                <span class="tag">Typography</span>
                <span class="tag">CSS Grid</span>
                <span class="tag">Web Design</span>
            </div>
            <p class="copyright">&copy; 2026 Elena Rostova. All rights reserved.</p>
        </footer>

    </main>

</body>
</html>
2. CSS Code (style.css)
CSS
/* --- Global Reset & Box Sizing --- */
* {
    box-sizing: border-box;
    margin: 0;
    padding: 0;
}

body {
    font-family: 'Inter', system-ui, -apple-system, sans-serif;
    background-color: #fafaf9;
    color: #1c1917;
    line-height: 1.7;
    padding: 24px 16px;
    overflow-x: hidden; /* Prevents horizontal screen overflow */
}

/* --- 5. Suitable Max-Width on the Content Container & Line Length Control --- */
.article-container {
    max-width: 720px; /* Optimal measure for comfortable reading (60-75 characters per line) */
    margin: 0 auto;
    background-color: #ffffff;
    border: 1px solid #e7e5e4;
    border-radius: 16px;
    padding: 32px 24px;
    box-shadow: 0 4px 6px -1px rgba(0, 0, 0, 0.02);
}

/* --- Article Header Typography & Spacing --- */
.article-header {
    margin-bottom: 32px;
}

.category {
    font-size: 0.85rem;
    font-weight: 600;
    text-transform: uppercase;
    letter-spacing: 1.5px;
    color: #d97706;
    display: inline-block;
    margin-bottom: 12px;
}

/* --- 3. Fluid Typography Using clamp() and rem --- */
h1 {
    font-family: 'Playfair Display', serif;
    font-size: clamp(2rem, 4vw + 1rem, 3.2rem); /* Scales fluidly between mobile and desktop */
    line-height: 1.2;
    font-weight: 700;
    color: #0c0a09;
    margin-bottom: 16px;
}

.subtitle {
    font-size: clamp(1rem, 1vw + 0.8rem, 1.2rem);
    color: #57534e;
    line-height: 1.6;
    margin-bottom: 24px;
}

.meta-info {
    display: flex;
    align-items: center;
    gap: 12px;
    padding-top: 16px;
    border-top: 1px solid #f5f5f4;
}

.author-avatar {
    width: 44px;
    height: 44px;
    border-radius: 50%;
    object-fit: cover;
}

.author-name {
    display: block;
    font-weight: 600;
    font-size: 0.95rem;
    color: #292524;
}

.publish-date {
    font-size: 0.8rem;
    color: #78716c;
}

/* --- 4. Responsive Images (max-width: 100% and height: auto) --- */
.image-wrapper {
    margin: 32px 0;
    text-align: center;
}

.image-wrapper img {
    width: 100%;           /* Fills container width */
    max-width: 100%;       /* Prevents overflow */
    height: auto;          /* Maintains correct aspect ratio without stretching */
    border-radius: 10px;
    display: block;
    box-shadow: 0 4px 12px rgba(0,0,0,0.06);
}

.image-wrapper figcaption {
    font-size: 0.85rem;
    color: #78716c;
    margin-top: 8px;
    font-style: italic;
}

/* --- Article Body Text Sizing & Spacing --- */
.article-body h2 {
    font-family: 'Playfair Display', serif;
    font-size: clamp(1.5rem, 2.5vw + 0.5rem, 2rem);
    font-weight: 600;
    color: #0c0a09;
    margin: 40px 0 16px 0;
}

.article-body p {
    font-size: 1.05rem; /* ~16.8px base scale using rem units */
    margin-bottom: 20px;
    color: #292524;
}

.article-body .lead {
    font-size: 1.2rem;
    font-weight: 400;
    color: #44403c;
    line-height: 1.6;
}

.article-body code {
    background-color: #f5f5f4;
    color: #b45309;
    padding: 2px 6px;
    border-radius: 4px;
    font-family: monospace;
    font-size: 0.9em;
}

/* --- Footer Section --- */
.article-footer {
    margin-top: 48px;
    padding-top: 24px;
    border-top: 1px solid #e7e5e4;
    display: flex;
    flex-direction: column;
    gap: 16px;
}

.tags {
    display: flex;
    gap: 8px;
    flex-wrap: wrap;
}

.tag {
    background-color: #f5f5f4;
    color: #57534e;
    padding: 4px 12px;
    border-radius: 20px;
    font-size: 0.8rem;
    font-weight: 500;
}

.copyright {
    font-size: 0.85rem;
    color: #78716c;
}

/* --- Desktop Scaling Adjustments --- */
@media (min-width: 768px) {
    body {
        padding: 40px 24px;
    }
    
    .article-container {
        padding: 48px 40px;
    }
}
Assignment Checklist & Verification:
Article/Portfolio Page Layout: Built a professional editorial article template.

Headings, Paragraphs, & Images: Included structured semantic markup with multiple headings, paragraphs, code snippets, and feature imagery.

rem & clamp() Typography: Utilized clamp() for headings and subtitle scaling so font sizes adapt smoothly across device viewports without abrupt jumps.

Responsive Images: Applied max-width: 100% and height: auto on .image-wrapper img to ensure images scale proportionally and never stretch or distort.

Container max-width: Set a strict limit of 720px on .article-container to maintain ideal line length (measure) for readability.

Line Length & Spacing: Optimized vertical rhythm (margin, padding, line-height: 1.7) for both compact mobile screens and spacious desktop viewports.

Overflow Prevention: Verified overflow-x: hidden on the body and robust image dimensions to prevent horizontal scrolling and text clipping.