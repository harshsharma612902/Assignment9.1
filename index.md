The HTML File (index.html)
HTML
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <!-- Step 2: Essential Viewport Meta Tag for Mobile Devices -->
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Mobile-First Responsive Page</title>
    <link rel="stylesheet" href="style.css">
</head>
<body>

    <!-- Header Section -->
    <header class="site-header">
        <div class="nav-container">
            <h1 class="logo">NexusApp</h1>
            <button class="menu-toggle" aria-label="Toggle navigation">☰</button>
            <nav class="nav-links">
                <a href="#features">Features</a>
                <a href="#pricing">Pricing</a>
                <a href="#about">About</a>
                <a href="#contact" class="btn-nav">Get Started</a>
            </nav>
        </div>
    </header>

    <!-- Main Content Area -->
    <main class="main-content">
        
        <!-- Hero Section -->
        <section class="hero">
            <div class="hero-text">
                <h2>Build Faster, Scale Smarter</h2>
                <p>A mobile-first workflow ensures your web application performs seamlessly across all handheld devices, tablets, and desktop workstations.</p>
                <a href="#cta" class="btn btn-primary">Start Free Trial</a>
            </div>
            <div class="hero-image">
                <img src="https://images.unsplash.com/photo-1551288049-bebda4e38f71?auto=format&fit=crop&q=80&w=500" alt="Mobile Dashboard Preview">
            </div>
        </section>

        <!-- Feature Cards Section (Step 1 & 3: Mobile-First Single Column) -->
        <section class="features-section">
            <h3>Core Features</h3>
            <div class="cards-grid">
                <article class="card">
                    <h4>Fluid Layouts</h4>
                    <p>Adapts fluidly to any screen width without horizontal scrolling.</p>
                </article>
                <article class="card">
                    <h4>Optimized Speed</h4>
                    <p>Lightweight CSS structure designed for rapid mobile loading times.</p>
                </article>
                <article class="card">
                    <h4>Modern Grid</h4>
                    <p>Built with native CSS Grid and Flexbox for precise alignment.</p>
                </article>
            </div>
        </section>

    </main>

    <!-- Footer Section -->
    <footer class="site-footer">
        <p>&copy; 2026 NexusApp Inc. All rights reserved.</p>
    </footer>

</body>
</html>
2. The CSS File (style.css)
CSS
/* ==========================================================================
   Step 3: Mobile-First Base Styles (Targeting Small Screens First)
   ========================================================================== */
* {
    box-sizing: border-box;
    margin: 0;
    padding: 0;
}

body {
    font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
    background-color: #f8fafc;
    color: #1e293b;
    line-height: 1.6;
    /* Step 7: Prevent unwanted horizontal overflow */
    width: 100%;
    overflow-x: hidden;
}

/* Header - Mobile Layout */
.site-header {
    background-color: #ffffff;
    border-bottom: 1px solid #e2e8f0;
    position: sticky;
    top: 0;
    z-index: 100;
}

.nav-container {
    padding: 16px;
    display: flex;
    justify-content: space-between;
    align-items: center;
}

.logo {
    font-size: 1.25rem;
    color: #2563eb;
    font-weight: 800;
}

.menu-toggle {
    background: none;
    border: none;
    font-size: 1.5rem;
    cursor: pointer;
    color: #1e293b;
}

/* Hide desktop nav links by default on mobile */
.nav-links {
    display: none; 
}

/* Main Content - Mobile Single Column Stack */
.main-content {
    padding: 24px 16px;
    display: flex;
    flex-direction: column;
    gap: 40px;
}

/* Hero Section - Mobile */
.hero {
    display: flex;
    flex-direction: column;
    gap: 24px;
    text-align: center;
}

.hero-text h2 {
    font-size: 2rem;
    color: #0f172a;
    margin-bottom: 12px;
    line-height: 1.2;
}

.hero-text p {
    color: #64748b;
    margin-bottom: 20px;
    font-size: 1rem;
}

.hero-image img {
    width: 100%;
    max-width: 400px;
    height: auto;
    border-radius: 8px;
    box-shadow: 0 4px 6px -1px rgba(0, 0, 0, 0.05);
}

/* Buttons - Mobile Touch Friendly */
.btn {
    display: inline-block;
    padding: 12px 24px;
    border-radius: 6px;
    font-weight: 600;
    text-decoration: none;
    text-align: center;
}

.btn-primary {
    background-color: #2563eb;
    color: white;
    width: 100%; /* Full width button on small mobile screens */
}

/* Features Section - Mobile Stack */
.features-section h3 {
    font-size: 1.5rem;
    margin-bottom: 16px;
    color: #0f172a;
}

.cards-grid {
    display: flex;
    flex-direction: column; /* Single column stack */
    gap: 16px;
}

.card {
    background-color: #ffffff;
    border: 1px solid #e2e8f0;
    border-radius: 8px;
    padding: 20px;
    box-shadow: 0 1px 3px rgba(0, 0, 0, 0.03);
}

.card h4 {
    font-size: 1.1rem;
    color: #0f172a;
    margin-bottom: 6px;
}

.card p {
    color: #64748b;
    font-size: 0.9rem;
}

/* Footer */
.site-footer {
    background-color: #ffffff;
    border-top: 1px solid #e2e8f0;
    padding: 20px 16px;
    text-align: center;
    font-size: 0.85rem;
    color: #64748b;
}


/* ==========================================================================
   Steps 4 & 5: Breakpoint 1 (Tablets - min-width: 640px)
   ========================================================================== */
@media (min-width: 640px) {
    .main-content {
        padding: 40px 32px;
    }

    .hero {
        text-align: left;
        flex-direction: row;
        align-items: center;
        justify-content: space-between;
    }

    .hero-text {
        flex: 1;
    }

    .hero-image {
        flex: 1;
        text-align: right;
    }

    .btn-primary {
        width: auto; /* Revert full-width button constraint */
    }

    /* Switch feature cards to a 2-column grid */
    .cards-grid {
        display: grid;
        grid-template-columns: repeat(2, 1fr);
        gap: 20px;
    }
}


/* ==========================================================================
   Steps 4 & 5: Breakpoint 2 (Desktops - min-width: 1024px)
   ========================================================================== */
@media (min-width: 1024px) {
    .nav-container {
        max-width: 1200px;
        margin: 0 auto;
        padding: 20px 40px;
    }

    /* Reveal desktop navigation links and hide mobile hamburger toggle */
    .menu-toggle {
        display: none;
    }

    .nav-links {
        display: flex;
        gap: 30px;
        align-items: center;
    }

    .nav-links a:not(.btn-nav) {
        text-decoration: none;
        color: #64748b;
        font-weight: 600;
        transition: color 0.2s;
    }

    .nav-links a:not(.btn-nav):hover {
        color: #2563eb;
    }

    .btn-nav {
        background-color: #eff6ff;
        color: #2563eb;
        padding: 8px 16px;
        border-radius: 6px;
        text-decoration: none;
        font-weight: 600;
    }

    .main-content {
        max-width: 1200px;
        margin: 0 auto;
        padding: 60px 40px;
    }

    .hero-text h2 {
        font-size: 3rem;
    }

    /* Switch feature cards to a 3-column grid */
    .cards-grid {
        grid-template-columns: repeat(3, 1fr);
        gap: 24px;
    }
}