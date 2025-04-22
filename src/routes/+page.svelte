<script>
    import { fade, slide } from 'svelte/transition'; // Import Svelte transitions
    import NavBar from '../lib/components/NavBar.svelte';
    import Footer from '../lib/components/Footer.svelte'; // Import the Footer component
</script>

<style>
    /* Subtle neon button effect */
    .neon-button {
        position: relative;
        display: inline-block;
        padding: 0.5rem 1rem; /* Adjusted for mobile */
        font-size: 0.875rem; /* Smaller font size for mobile */
        font-weight: bold;
        color: white;
        text-transform: uppercase;
        background: transparent;
        border: 2px solid #42e695;
        border-radius: 0.5rem;
        overflow: hidden;
        transition: color 0.3s ease, box-shadow 0.3s ease, background-color 0.3s ease;
        box-shadow: 0 0 5px #42e695, 0 0 10px #42e695;
    }

    .neon-button::before {
        content: '';
        position: absolute;
        top: 0;
        left: 0;
        width: 100%;
        height: 100%;
        background: linear-gradient(90deg, #42e695, #7873f5);
        background-size: 200% 200%;
        z-index: -1;
        transition: opacity 0.3s ease;
        opacity: 0;
        border-radius: inherit;
    }

    .neon-button:hover::before {
        opacity: 0.5;
        animation: subtle-neon 4s linear infinite;
    }

    .neon-button:hover {
        color: #42e695;
        background-color: rgba(66, 230, 149, 0.1);
        box-shadow: 0 0 10px #42e695, 0 0 20px #42e695;
    }

    @keyframes subtle-neon {
        0% {
            background-position: 0% 50%;
        }
        50% {
            background-position: 100% 50%;
        }
        100% {
            background-position: 0% 50%;
        }
    }
</style>

<svelte:head>
    <title>Portfol.io</title>
    <meta name="description" content="Welcome to Portfol.io, a team of passionate developers creating innovative and impactful projects." />
</svelte:head >

<NavBar />

<main class="flex-grow">
    <!-- Hero Section -->
    <section id="hero" class="text-center py-20 bg-gray-800 text-white">
        <div class="max-w-screen-lg mx-auto" in:fade={{ duration: 800 }}>
            <h1 class="text-2xl font-bold mb-4 sm:text-3xl lg:text-4xl">
                Welcome to Portfol.io
            </h1>
            <p class="text-sm mb-6 sm:text-base lg:text-lg">
                We are a team of passionate developers creating innovative and impactful projects.
            </p>
            <a href="/team" class="neon-button">
                Meet Our Team
            </a>
        </div>
    </section>

    <!-- Team Section -->
    <section id="team" class="py-16 px-4 sm:px-8 bg-gray-900 text-gray-100">
        <div class="max-w-screen-lg mx-auto">
            <h2 class="text-2xl font-bold mb-6 sm:text-3xl lg:text-3xl" in:slide={{ duration: 600 }}>
                Meet the Team
            </h2>
            <div class="grid grid-cols-1 sm:grid-cols-2 lg:grid-cols-3 gap-6">
                <div class="text-center" in:fade={{ duration: 500 }}>
                    <a href="/team/irish">
                        <img src="/img/img1.jpg" alt="Irish M. Villanueva" class="rounded-xl mx-auto mb-3 w-full sm:w-48 h-auto object-cover">
                    </a>
                    <h3 class="text-lg font-semibold sm:text-xl">Irish M. Villanueva</h3>
                    <p class="text-sm sm:text-base">BS-Tourism</p>
                </div>
                <div class="text-center" in:fade={{ duration: 500 }}>
                    <a href="/team/brent">
                        <img src="/img/img3.jpg" alt="Brent Kenneth O. Abrazaldo" class="rounded-xl mx-auto mb-3 w-full sm:w-48 h-auto object-cover">
                    </a>
                    <h3 class="text-lg font-semibold sm:text-xl">Brent Kenneth O. Abrazaldo</h3>
                    <p class="text-sm sm:text-base">BS-Computer Science</p>
                </div>
                <div class="text-center" in:fade={{ duration: 500 }}>
                    <a href="/team/shaira">
                        <img src="/img/img2.jpg" alt="Shaira Embornal" class="rounded-xl mx-auto mb-3 w-full sm:w-48 h-auto object-cover">
                    </a>
                    <h3 class="text-lg font-semibold sm:text-xl">Shaira Embornal</h3>
                    <p class="text-sm sm:text-base">BS-Tourism</p>
                </div>
            </div>
        </div>
    </section>
</main>

<Footer />