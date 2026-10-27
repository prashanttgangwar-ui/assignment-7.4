## 1. Aim
To create a modern and responsive landing page header and hero section using HTML and CSS Flexbox.

## 2. Objective
- To create a header with a logo, navigation links, and a CTA button.
- To design an attractive hero section with a heading, paragraph, and buttons.
- To add an illustration to the landing page.
- To arrange text and image side-by-side using Flexbox.
- To align the hero content properly.
- To create a footer section using CSS.
- To make the webpage responsive for desktop, tablet, and mobile devices.

## 3. Technologies Used
- HTML5
- CSS3
- Flexbox
- Media Queries
- Google Fonts
- Unsplash Image

## 4. Complete Source Code

Create a file named `index.html` and copy the following complete code into it.

### index.html

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">

    <title>NovaSpace | Build Your Future</title>

    <meta
        name="description"
        content="Discover smarter digital solutions and grow your ideas with NovaSpace."
    >

    <link rel="preconnect" href="https://fonts.googleapis.com">
    <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>

    <link
        href="https://fonts.googleapis.com/css2?family=Poppins:wght@400;500;600;700;800&display=swap"
        rel="stylesheet"
    >

    <style>
        /* Reset and Global Styles */

        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }

        html {
            scroll-behavior: smooth;
        }

        body {
            font-family: "Poppins", sans-serif;
            background-color: #f8faff;
            color: #172554;
            line-height: 1.6;
        }

        a {
            text-decoration: none;
            color: inherit;
        }

        button {
            font-family: inherit;
            cursor: pointer;
        }

        .container {
            width: 90%;
            max-width: 1200px;
            margin: 0 auto;
        }

        /* Header Section */

        .header {
            width: 100%;
            background-color: #ffffff;
            border-bottom: 1px solid #e5eaf5;
            position: sticky;
            top: 0;
            z-index: 1000;
        }

        .navbar {
            min-height: 82px;
            display: flex;
            justify-content: space-between;
            align-items: center;
            gap: 24px;
        }

        .logo {
            display: flex;
            align-items: center;
            gap: 10px;
            font-size: 27px;
            font-weight: 800;
            color: #2563eb;
            white-space: nowrap;
        }

        .logo-icon {
            width: 42px;
            height: 42px;
            display: flex;
            justify-content: center;
            align-items: center;
            border-radius: 12px;
            color: #ffffff;
            background: linear-gradient(135deg, #2563eb, #7c3aed);
            font-size: 23px;
        }

        .nav-links {
            display: flex;
            align-items: center;
            gap: 30px;
            list-style: none;
        }

        .nav-links a {
            font-size: 14px;
            font-weight: 500;
            color: #475569;
            transition: color 0.3s ease;
        }

        .nav-links a:hover {
            color: #2563eb;
        }

        .header-btn {
            padding: 12px 22px;
            border: none;
            border-radius: 9px;
            background-color: #2563eb;
            color: #ffffff;
            font-size: 14px;
            font-weight: 600;
            white-space: nowrap;
            transition: background-color 0.3s ease;
        }

        .header-btn:hover {
            background-color: #1d4ed8;
        }

        /* Hero Section */

        .hero {
            padding: 75px 0 85px;
            background:
                radial-gradient(
                    circle at 85% 20%,
                    #e0eaff 0,
                    transparent 35%
                ),
                #f8faff;
        }

        .hero-content {
            display: flex;
            justify-content: space-between;
            align-items: center;
            gap: 55px;
        }

        .hero-text {
            flex: 1;
            max-width: 560px;
        }

        .tagline {
            display: inline-block;
            padding: 8px 15px;
            margin-bottom: 22px;
            border: 1px solid #bfdbfe;
            border-radius: 50px;
            background-color: #eff6ff;
            color: #2563eb;
            font-size: 13px;
            font-weight: 600;
        }

        .hero-text h1 {
            margin-bottom: 22px;
            font-size: clamp(36px, 4.5vw, 58px);
            line-height: 1.2;
            letter-spacing: -1.8px;
            color: #172554;
        }

        .hero-text h1 span {
            color: #2563eb;
        }

        .hero-text p {
            max-width: 500px;
            margin-bottom: 30px;
            color: #64748b;
            font-size: 16px;
            line-height: 1.9;
        }

        .hero-buttons {
            display: flex;
            align-items: center;
            flex-wrap: wrap;
            gap: 15px;
        }

        .primary-btn {
            display: inline-block;
            padding: 14px 25px;
            border: 2px solid #2563eb;
            border-radius: 9px;
            background-color: #2563eb;
            color: #ffffff;
            font-size: 14px;
            font-weight: 600;
            transition: all 0.3s ease;
        }

        .primary-btn:hover {
            background-color: #1d4ed8;
            border-color: #1d4ed8;
            transform: translateY(-2px);
        }

        .secondary-btn {
            display: inline-block;
            padding: 14px 25px;
            border: 2px solid #dbe4f0;
            border-radius: 9px;
            background-color: #ffffff;
            color: #172554;
            font-size: 14px;
            font-weight: 600;
            transition: all 0.3s ease;
        }

        .secondary-btn:hover {
            border-color: #2563eb;
            color: #2563eb;
            transform: translateY(-2px);
        }

        /* Hero Image */

        .hero-image {
            flex: 1;
            min-width: 0;
            position: relative;
        }

        .hero-image img {
            display: block;
            width: 100%;
            max-width: 540px;
            height: 420px;
            margin-left: auto;
            object-fit: cover;
            border-radius: 24px;
            box-shadow: 0 25px 60px rgba(37, 99, 235, 0.15);
        }

        .floating-card {
            position: absolute;
            bottom: 25px;
            left: -25px;
            padding: 16px 20px;
            border: 1px solid #edf2fa;
            border-radius: 14px;
            background-color: #ffffff;
            box-shadow: 0 12px 35px rgba(15, 23, 42, 0.12);
        }

        .floating-card strong {
            display: block;
            color: #2563eb;
            font-size: 20px;
        }

        .floating-card span {
            color: #64748b;
            font-size: 12px;
        }

        /* Features Section */

        .features {
            padding: 35px 0;
            border-top: 1px solid #e5eaf5;
            background-color: #ffffff;
        }

        .feature-list {
            display: flex;
            justify-content: space-around;
            align-items: center;
            flex-wrap: wrap;
            gap: 20px;
        }

        .feature-item {
            display: flex;
            align-items: center;
            gap: 10px;
            color: #475569;
            font-size: 14px;
            font-weight: 500;
        }

        .feature-check {
            display: flex;
            justify-content: center;
            align-items: center;
            width: 25px;
            height: 25px;
            border-radius: 50%;
            background-color: #dcfce7;
            color: #15803d;
            font-weight: 700;
        }

        /* Footer Section */

        .footer {
            padding: 25px 0;
            background-color: #172554;
            color: #cbd5e1;
            text-align: center;
        }

        .footer p {
            font-size: 13px;
        }

        .footer a {
            color: #93c5fd;
        }

        .footer a:hover {
            color: #ffffff;
        }

        /* Tablet Responsive Design */

        @media (max-width: 900px) {
            .navbar {
                gap: 15px;
            }

            .nav-links {
                gap: 15px;
            }

            .hero {
                padding: 55px 0 65px;
            }

            .hero-content {
                gap: 30px;
            }

            .hero-image img {
                height: 350px;
            }

            .floating-card {
                left: -12px;
            }
        }

        /* Mobile Responsive Design */

        @media (max-width: 650px) {
            .navbar {
                min-height: auto;
                padding: 16px 0;
                flex-wrap: wrap;
            }

            .logo {
                font-size: 23px;
            }

            .logo-icon {
                width: 36px;
                height: 36px;
                font-size: 20px;
            }

            .nav-links {
                order: 3;
                width: 100%;
                justify-content: center;
                flex-wrap: wrap;
                gap: 12px 20px;
            }

            .nav-links a {
                font-size: 12px;
            }

            .header-btn {
                padding: 10px 14px;
                font-size: 12px;
            }

            .hero {
                padding: 45px 0 55px;
            }

            .hero-content {
                flex-direction: column;
                align-items: stretch;
                gap: 40px;
            }

            .hero-text {
                max-width: 100%;
            }

            .hero-text h1 {
                font-size: 38px;
                letter-spacing: -1px;
            }

            .hero-text p {
                font-size: 14px;
            }

            .hero-buttons {
                gap: 10px;
            }

            .primary-btn,
            .secondary-btn {
                padding: 12px 16px;
                font-size: 13px;
            }

            .hero-image img {
                max-width: 100%;
                height: 280px;
                border-radius: 18px;
            }

            .floating-card {
                bottom: 15px;
                left: 12px;
                padding: 12px 16px;
            }

            .floating-card strong {
                font-size: 17px;
            }

            .feature-list {
                justify-content: flex-start;
                padding-left: 10px;
                gap: 18px;
            }

            .feature-item {
                font-size: 12px;
            }
        }

        /* Extra Small Screens */

        @media (max-width: 380px) {
            .container {
                width: 92%;
            }

            .logo {
                font-size: 20px;
            }

            .header-btn {
                padding: 9px 10px;
            }

            .hero-text h1 {
                font-size: 32px;
            }

            .hero-buttons {
                align-items: stretch;
                flex-direction: column;
            }

            .primary-btn,
            .secondary-btn {
                text-align: center;
            }
        }
    </style>
</head>

<body>

    <!-- Header Section -->

    <header class="header">
        <div class="container navbar">

            <a href="#home" class="logo" aria-label="NovaSpace home">
                <span class="logo-icon">N</span>
                NovaSpace
            </a>

            <nav aria-label="Main navigation">
                <ul class="nav-links">
                    <li><a href="#home">Home</a></li>
                    <li><a href="#features">Features</a></li>
                    <li><a href="#about">About</a></li>
                    <li><a href="#contact">Contact</a></li>
                </ul>
            </nav>

            <a href="#contact" class="header-btn">Get Started &rarr;</a>

        </div>
    </header>

    <!-- Hero Section -->

    <main>
        <section class="hero" id="home">
            <div class="container hero-content">

                <div class="hero-text">

                    <span class="tagline">
                        ✨ YOUR IDEAS, OUR INNOVATION
                    </span>

                    <h1>
                        Build Your Future
                        <span>With Smart Ideas.</span>
                    </h1>

                    <p>
                        Turn your ideas into reality with modern digital
                        solutions. Explore new possibilities, improve your
                        workflow, and take your next big step with NovaSpace.
                    </p>

                    <div class="hero-buttons">
                        <a href="#contact" class="primary-btn">
                            Get Started &rarr;
                        </a>

                        <a href="#features" class="secondary-btn">
                            Explore Features
                        </a>
                    </div>

                </div>

                <div class="hero-image" id="about">

                    <img
                        src="https://images.unsplash.com/photo-1497366754035-f200968a6e72?auto=format&fit=crop&w=1100&q=85"
                        alt="Modern and bright creative workspace"
                    >

                    <div class="floating-card">
                        <strong>100% Creative</strong>
                        <span>Ideas into possibilities</span>
                    </div>

                </div>

            </div>
        </section>

        <!-- Features Section -->

        <section class="features" id="features">
            <div class="container feature-list">

                <div class="feature-item">
                    <span class="feature-check">✓</span>
                    Modern Design
                </div>

                <div class="feature-item">
                    <span class="feature-check">✓</span>
                    Easy to Use
                </div>

                <div class="feature-item">
                    <span class="feature-check">✓</span>
                    Responsive Layout
                </div>

                <div class="feature-item">
                    <span class="feature-check">✓</span>
                    Creative Solutions
                </div>

            </div>
        </section>
    </main>

    <!-- Footer Section -->

    <footer class="footer" id="contact">
        <div class="container">
            <p>
                &copy; 2026 NovaSpace. All rights reserved.
                | Designed with HTML and CSS
                | <a href="#home">Back to Top ↑</a>
            </p>
        </div>
    </footer>

</body>
</html>
```

## 5. How the Code Works

1. **HTML5:** Creates the structure of the header, navigation, hero section, features, and footer.
2. **CSS Flexbox:** Uses `display: flex`, `justify-content`, `align-items`, and `gap` to arrange and align elements.
3. **Hero Section:** Displays the main heading, paragraph, CTA buttons, and image side-by-side.
4. **Sticky Header:** Uses `position: sticky` and `top: 0` to keep the navigation visible while scrolling.
5. **Responsive Design:** Uses media queries at `900px`, `650px`, and `380px` to adjust the layout for different screen sizes.
6. **Hover Effects:** Adds transitions to buttons and navigation links for a modern appearance.
7. **Footer:** Displays copyright information and a back-to-top link.

## 6. Expected Output

The webpage displays:
- A white header containing the NovaSpace logo, navigation links, and Get Started button.
- A modern hero section with a large heading, descriptive paragraph, two CTA buttons, and a workspace image.
- A floating information card over the image.
- A features section with four benefits.
- A dark footer with copyright information.
- A responsive layout that adapts to desktop, tablet, and mobile screens.

## 7. Testing and Responsiveness

Test the webpage in Google Chrome.

1. Open `index.html` in the browser.
2. Right-click the page and select **Inspect**.
3. Click the **Toggle Device Toolbar** icon to test mobile and tablet sizes.
4. Test widths such as 1440px, 768px, 390px, and 320px.
5. Check that navigation, buttons, text, and image remain properly aligned.
6. Check that the hero text and image stack vertically on mobile screens.
7. Verify that the external image loads with an internet connection.

## 8. Result

Successfully created a modern, attractive, and responsive landing page header and hero section using HTML5, CSS3, and Flexbox. The webpage includes navigation links, CTA buttons, an image, a features section, a sticky header, and a footer, and adapts to different screen sizes.
