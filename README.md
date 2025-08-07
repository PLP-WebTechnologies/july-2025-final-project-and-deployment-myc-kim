[![Review Assignment Due Date](https://classroom.github.com/assets/deadline-readme-button-22041afd0340ce965d47ae6ef1cefeee28c7c493a6346c4f15d667ab976d596c.svg)](https://classroom.github.com/a/Im5yaf49)
# 📦 Final Assignment: Build, Organize, and Deploy a Multipage Website

You're now ready to bring everything together—HTML, CSS, JavaScript, planning, structure, and deployment. This final project challenges you to **conceptualize, build, and deploy a multi-page website** that is responsive, interactive, and ready for the real world.

This assignment will guide you from planning your site all the way to deploying it online. Let’s make your project *production-worthy*! 🚀

---

## 🌐🎯 Part 1: Planning and Organizing a Multipage Website

Before you write any code, take time to plan:

* Define your website's purpose (portfolio, product showcase, blog, etc.)
* Outline 3–5 pages (e.g., Home, About, Services, Contact, Gallery)
* Sketch or describe the layout of each page
* Map out internal navigation (how pages link to one another)

**Goal:** Show intentional structure and user journey across the site.

---

## 🌍💻 Part 2: Build the Website Using HTML5, CSS, and JavaScript

Using your plan, begin building:

* Use HTML5 for semantic structure
* Apply CSS for responsive layout, styling, and animations
* Use JavaScript to add interactivity (menus, forms, toggles, dynamic content)

Each page should:

* Be mobile-responsive
* Share a consistent layout/header/footer
* Include at least one interactive element (e.g., form validation, toggle menu, animation on scroll)

**Goal:** Integrate everything you’ve learned in a cohesive, functioning project.

---

## 🛠️🚀 Part 3: Best Practices for Code Organization

Before deployment, refactor your project to follow production-friendly practices:

* Organize files in folders (`/css`, `/js`, `/images`, etc.)
* Write clean, modular, and commented code
* Use meaningful file names and relative paths
* Validate your HTML/CSS and test on different screen sizes

**Goal:** Prepare your codebase to be readable, maintainable, and scalable.

---

## 🌐🚀 Part 4: Introduction to Hosting and Deployment

Once your project is complete, choose a method to **host your site online**.

You can use:

* **GitHub Pages** (great for portfolios and static sites)
* **Netlify** (powerful CI/CD features and easy form support)
* **Vercel** (lightning-fast deployment for frontend projects)

Deploy your project and confirm that:

* All links and scripts work
* It loads properly on mobile and desktop
* It has a clear, shareable URL

**Goal:** Publish your work online and make it accessible to the world.

---

## Deliverables

1. A GitHub repository containing:

   * Your complete project code, properly organized
   * A `README.md` file explaining your project purpose, structure, and live URL
2. A live deployed website (hosted via GitHub Pages, Netlify, or Vercel)

---

## Outcome

* Clarity and thoroughness of planning documentation
* Proper use of HTML5, CSS, and JavaScript across multiple pages
* Responsive and accessible design
* Clean, well-organized, and commented code
* Successful live deployment with a working link
* Evidence of following best practices


MY PROJECT:

  <!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>My Portfolio</title>
    <script src="https://cdn.tailwindcss.com"></script>
    <style>
        @import url('https://fonts.googleapis.com/css2?family=Inter:wght@400;600;700&display=swap');
        body {
            font-family: 'Inter', sans-serif;
            background-color: #f8fafc;
            color: #334155;
            transition: background-color 0.3s ease;
        }

        .dark body {
            background-color: #1e293b;
            color: #f1f5f9;
        }
        .section-content {
            display: none;
            animation: fadeIn 0.5s ease-in-out;
        }
        .section-content.active {
            display: block;
        }
        @keyframes fadeIn {
            from { opacity: 0; transform: translateY(20px); }
            to { opacity: 1; transform: translateY(0); }
        }
        .nav-link {
            transition: color 0.2s ease, transform 0.2s ease;
        }
        .nav-link:hover {
            transform: scale(1.05);
            color: #4f46e5;
        }
        .dark .nav-link:hover {
            color: #818cf8;
        }
    </style>
</head>
<body class="relative">

    <!-- Mobile Menu Overlay -->
    <div id="mobile-menu-overlay" class="fixed inset-0 bg-gray-800 bg-opacity-75 z-40 hidden md:hidden transition-opacity duration-300 opacity-0"></div>

    <!-- Header and Navigation -->
    <header class="bg-white dark:bg-gray-800 shadow-md sticky top-0 z-50 transition-colors duration-300">
        <nav class="container mx-auto p-4 flex justify-between items-center">
            <a href="#" class="text-xl font-bold text-gray-900 dark:text-white">Michael's Portfolio</a>
            
            <!-- Desktop Navigation -->
            <div class="hidden md:flex space-x-6 text-gray-600 dark:text-gray-300">
                <a href="#home" class="nav-link">Home</a>
                <a href="#about" class="nav-link">About</a>
                <a href="#portfolio" class="nav-link">Portfolio</a>
                <a href="#contact" class="nav-link">Contact</a>
            </div>

            <!-- Mobile Menu Button -->
            <button id="menu-button" class="md:hidden p-2 rounded-md focus:outline-none focus:ring-2 focus:ring-indigo-500 text-gray-600 dark:text-gray-300">
                <svg xmlns="http://www.w3.org/2000/svg" class="h-6 w-6" fill="none" viewBox="0 0 24 24" stroke="currentColor">
                    <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M4 6h16M4 12h16M4 18h16" />
                </svg>
            </button>
            
            <!-- Theme Toggle -->
            <button id="theme-toggle" class="p-2 rounded-md focus:outline-none focus:ring-2 focus:ring-indigo-500 text-gray-600 dark:text-gray-300">
                <svg xmlns="http://www.w3.org/2000/svg" class="h-6 w-6" fill="none" viewBox="0 0 24 24" stroke="currentColor">
                    <path d="M12 3v1m0 16v1m9-9h-1m-16 0H3m15.542 3.542l-.707.707M6.172 6.172l-.707-.707M18.542 8.458l.707-.707M6.172 17.828l-.707.707M12 18a6 6 0 100-12 6 6 0 000 12z" />
                </svg>
            </button>

            <!-- Mobile Menu -->
            <div id="mobile-menu" class="fixed top-0 right-0 h-full w-2/3 bg-white dark:bg-gray-800 shadow-lg z-50 transform translate-x-full transition-transform duration-300 md:hidden">
                <div class="p-6">
                    <div class="flex justify-end">
                        <button id="close-menu-button" class="p-2 rounded-md focus:outline-none focus:ring-2 focus:ring-indigo-500 text-gray-600 dark:text-gray-300">
                            <svg xmlns="http://www.w3.org/2000/svg" class="h-6 w-6" fill="none" viewBox="0 0 24 24" stroke="currentColor">
                                <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M6 18L18 6M6 6l12 12" />
                            </svg>
                        </button>
                    </div>
                    <nav class="flex flex-col space-y-4 mt-6 text-gray-600 dark:text-gray-300">
                        <a href="#home" class="nav-link text-lg block">Home</a>
                        <a href="#about" class="nav-link text-lg block">About</a>
                        <a href="#portfolio" class="nav-link text-lg block">Portfolio</a>
                        <a href="#contact" class="nav-link text-lg block">Contact</a>
                    </nav>
                </div>
            </div>

        </nav>
    </header>

    <!-- Main Content -->
    <main class="container mx-auto p-8 py-12">
        <!-- Home Section -->
        <section id="home" class="section-content active">
            <h1 class="text-4xl md:text-6xl font-extrabold text-center mb-6 text-indigo-600 dark:text-indigo-400">Hello, I'm Michael Irungu or popuraly known as Myckim</h1>
            <p class="text-xl md:text-2xl text-center mb-12 max-w-2xl mx-auto">I'm a full-stack developer with a passion for building beautiful and functional web applications.</p>
            <div class="flex justify-center">
                <a href="#contact" class="bg-indigo-600 text-white font-bold py-3 px-8 rounded-full shadow-lg hover:bg-indigo-700 transition-colors duration-300">Get in Touch</a>
            </div>
        </section>

        <!-- About Section -->
        <section id="about" class="section-content">
            <h2 class="text-3xl md:text-4xl font-bold mb-6 text-center text-indigo-600 dark:text-indigo-400">About Me</h2>
            <div class="max-w-3xl mx-auto text-lg space-y-4">
                <p>I am a versatile software developer with over 5 years of experience in creating dynamic and responsive web applications. My expertise spans across front-end and back-end technologies, allowing me to handle every aspect of the development lifecycle.</p>
                <p>I enjoy solving complex problems and collaborating with teams to deliver high-quality products. I am constantly learning new technologies and improving my skills to stay current in the fast-paced world of web development.</p>
            </div>
        </section>

        <!-- Portfolio Section -->
        <section id="portfolio" class="section-content">
            <h2 class="text-3xl md:text-4xl font-bold mb-6 text-center text-indigo-600 dark:text-indigo-400">My Work</h2>
            <div class="grid grid-cols-1 md:grid-cols-2 lg:grid-cols-3 gap-8">
                <!-- Project 1 -->
                <div class="bg-white dark:bg-gray-700 rounded-lg shadow-md overflow-hidden hover:shadow-xl transition-shadow duration-300">
                    <img src="https://placehold.co/600x400/10b981/ffffff?text=Project+1" alt="Project 1" class="w-full h-48 object-cover">
                    <div class="p-6">
                        <h3 class="font-bold text-xl mb-2 text-gray-900 dark:text-white">Project One - Weather App</h3>
                        <p class="text-gray-600 dark:text-gray-300">A dynamic weather application built with HTML, CSS, and JavaScript that fetches real-time weather data from a third-party API. This project showcases my ability to handle API calls, parse JSON data, and dynamically update the DOM based on a user's location or search query.</p>
                    </div>
                </div>
                <!-- Project 2 -->
                <div class="bg-white dark:bg-gray-700 rounded-lg shadow-md overflow-hidden hover:shadow-xl transition-shadow duration-300">
                    <img src="https://placehold.co/600x400/818cf8/ffffff?text=Project+2" alt="Project 2" class="w-full h-48 object-cover">
                    <div class="p-6">
                        <h3 class="font-bold text-xl mb-2 text-gray-900 dark:text-white">Project Two - To-Do List App</h3>
                        <p class="text-gray-600 dark:text-gray-300">An interactive to-do list application built using vanilla JavaScript. This project allows users to add, edit, and delete tasks, as well as mark them as complete. It demonstrates my proficiency with DOM manipulation, event handling, and a simple data model.</p>
                    </div>
                </div>
                <!-- Project 3 -->
                <div class="bg-white dark:bg-gray-700 rounded-lg shadow-md overflow-hidden hover:shadow-xl transition-shadow duration-300">
                    <img src="https://placehold.co/600x400/9b59b6/ffffff?text=Project+3" alt="Project 3" class="w-full h-48 object-cover">
                    <div class="p-6">
                        <h3 class="font-bold text-xl mb-2 text-gray-900 dark:text-white">Project Three - Guess the Number Game</h3>
                        <p class="text-gray-600 dark:text-gray-300">A simple and fun browser-based game where a user tries to guess a randomly generated number. This project demonstrates core JavaScript concepts such as random number generation, conditional statements for game logic, and providing real-time feedback to the user on their guesses.</p>
                    </div>
                </div>
            </div>
        </section>

        <!-- Contact Section -->
        <section id="contact" class="section-content">
            <h2 class="text-3xl md:text-4xl font-bold mb-6 text-center text-indigo-600 dark:text-indigo-400">Get in Touch</h2>
            <div class="max-w-lg mx-auto">
                <form id="contact-form" class="bg-white dark:bg-gray-700 p-8 rounded-lg shadow-md space-y-6">
                    <div>
                        <label for="name" class="block text-gray-700 dark:text-gray-300 font-bold mb-2">Name</label>
                        <input type="text" id="name" name="name" required class="w-full px-4 py-2 border border-gray-300 rounded-md focus:outline-none focus:ring-2 focus:ring-indigo-500 bg-gray-50 dark:bg-gray-800 dark:border-gray-600 dark:text-white">
                    </div>
                    <div>
                        <label for="email" class="block text-gray-700 dark:text-gray-300 font-bold mb-2">Email</label>
                        <input type="email" id="email" name="email" required class="w-full px-4 py-2 border border-gray-300 rounded-md focus:outline-none focus:ring-2 focus:ring-indigo-500 bg-gray-50 dark:bg-gray-800 dark:border-gray-600 dark:text-white">
                    </div>
                    <div>
                        <label for="message" class="block text-gray-700 dark:text-gray-300 font-bold mb-2">Message</label>
                        <textarea id="message" name="message" rows="4" required class="w-full px-4 py-2 border border-gray-300 rounded-md focus:outline-none focus:ring-2 focus:ring-indigo-500 bg-gray-50 dark:bg-gray-800 dark:border-gray-600 dark:text-white"></textarea>
                    </div>
                    <div id="form-message" class="text-center font-semibold"></div>
                    <button type="submit" class="w-full bg-indigo-600 text-white font-bold py-3 px-4 rounded-md hover:bg-indigo-700 transition-colors duration-300">Send Message</button>
                </form>
            </div>
        </section>
    </main>

    <!-- Footer -->
    <footer class="bg-white dark:bg-gray-800 p-4 text-center text-gray-600 dark:text-gray-400 transition-colors duration-300">
        <p>&copy; 2025 Michael's Portfolio. All rights reserved.</p>
    </footer>

    <script>
        document.addEventListener('DOMContentLoaded', () => {
            // --- Part 1: Page Navigation and Active State ---
            const navLinks = document.querySelectorAll('a[href^="#"]');
            const sections = document.querySelectorAll('.section-content');

            // Function to show a specific section
            function showSection(id) {
                sections.forEach(section => {
                    section.classList.remove('active');
                });
                const activeSection = document.querySelector(id);
                if (activeSection) {
                    activeSection.classList.add('active');
                    // Scroll to the top of the content smoothly
                    window.scrollTo({ top: 0, behavior: 'smooth' });
                }
            }

            // Handle initial page load and URL hash
            const initialHash = window.location.hash || '#home';
            showSection(initialHash);

            // Handle navigation clicks
            navLinks.forEach(link => {
                link.addEventListener('click', (e) => {
                    e.preventDefault();
                    const targetId = link.getAttribute('href');
                    history.pushState(null, '', targetId); // Update URL without page reload
                    showSection(targetId);
                    
                    // Close mobile menu if open
                    const mobileMenu = document.getElementById('mobile-menu');
                    if (!mobileMenu.classList.contains('translate-x-full')) {
                        mobileMenu.classList.add('translate-x-full');
                        document.getElementById('mobile-menu-overlay').classList.add('hidden');
                        document.body.style.overflow = '';
                    }
                });
            });

            // --- Part 2: Mobile Navigation Toggle ---
            const menuButton = document.getElementById('menu-button');
            const closeMenuButton = document.getElementById('close-menu-button');
            const mobileMenu = document.getElementById('mobile-menu');
            const mobileMenuOverlay = document.getElementById('mobile-menu-overlay');

            menuButton.addEventListener('click', () => {
                mobileMenu.classList.remove('translate-x-full');
                mobileMenuOverlay.classList.remove('hidden');
                setTimeout(() => mobileMenuOverlay.style.opacity = '1', 10);
                document.body.style.overflow = 'hidden'; // Prevent scrolling on main body
            });

            closeMenuButton.addEventListener('click', () => {
                mobileMenu.classList.add('translate-x-full');
                mobileMenuOverlay.style.opacity = '0';
                setTimeout(() => mobileMenuOverlay.classList.add('hidden'), 300);
                document.body.style.overflow = '';
            });

            mobileMenuOverlay.addEventListener('click', () => {
                mobileMenu.classList.add('translate-x-full');
                mobileMenuOverlay.style.opacity = '0';
                setTimeout(() => mobileMenuOverlay.classList.add('hidden'), 300);
                document.body.style.overflow = '';
            });
            
            // --- Part 3: Contact Form Validation and Submission ---
            const contactForm = document.getElementById('contact-form');
            const formMessage = document.getElementById('form-message');

            contactForm.addEventListener('submit', (e) => {
                e.preventDefault();
                
                const name = document.getElementById('name').value;
                const email = document.getElementById('email').value;
                const message = document.getElementById('message').value;

                if (name && email && message) {
                    formMessage.textContent = 'Message sent successfully! (This is a demo)';
                    formMessage.style.color = '#10b981'; // Green color
                    contactForm.reset();
                    
                    // Clear the message after a few seconds
                    setTimeout(() => {
                        formMessage.textContent = '';
                    }, 5000);
                } else {
                    formMessage.textContent = 'Please fill out all fields.';
                    formMessage.style.color = '#ef4444'; // Red color
                }
            });

            // --- Part 4: Theme Toggle (Dark/Light Mode) ---
            const themeToggle = document.getElementById('theme-toggle');
            const currentTheme = localStorage.getItem('theme');

            // Apply saved theme on page load
            if (currentTheme) {
                document.body.classList.add(currentTheme);
            }

            themeToggle.addEventListener('click', () => {
                document.body.classList.toggle('dark');
                let theme = 'light';
                if (document.body.classList.contains('dark')) {
                    theme = 'dark';
                }
                localStorage.setItem('theme', theme);
            });
        });
    </script>
</body>
</html>
