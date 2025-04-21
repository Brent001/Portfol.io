<script>
    import Footer from '$lib/components/Footer.svelte';
    import NavBar from '$lib/components/NavBar.svelte';
    import { fade } from 'svelte/transition';
</script>

<NavBar />

<main class="flex-grow py-8 px-4 sm:py-12 sm:px-6 bg-gray-900 text-gray-100">
    <!-- Hero Section -->
    <section class="max-w-screen-lg mx-auto text-center">
        <h1 class="text-2xl sm:text-4xl font-extrabold text-white" in:fade={{ duration: 500 }}>
            Portfol.io Website
        </h1>
        <p class="mt-4 text-sm sm:text-lg text-gray-300" in:fade={{ duration: 700 }}>
            A modern and responsive portfolio website showcasing our team's projects, skills, and creativity.
        </p>
    </section>

    <!-- Project Details Section -->
    <section class="mt-8 sm:mt-12 max-w-screen-lg mx-auto">
        <!-- Go Back Button -->
        <div class="mb-6 text-left">
            <button
                type="button"
                class="inline-flex items-center bg-gray-700 hover:bg-gray-800 text-white font-medium py-2 px-3 rounded-md shadow-md transition duration-300"
                on:click={() => window.history.back()}
            >
                <svg
                    xmlns="http://www.w3.org/2000/svg"
                    class="w-4 h-4 mr-2"
                    fill="none"
                    viewBox="0 0 24 24"
                    stroke="currentColor"
                    stroke-width="2"
                >
                    <path stroke-linecap="round" stroke-linejoin="round" d="M10 19l-7-7m0 0l7-7m-7 7h18" />
                </svg>
                Go Back
            </button>
        </div>

        <div class="bg-gray-800 rounded-lg shadow-lg overflow-hidden">
            <img src="/img/projects/portfol.io-banner.png" alt="Portfol.io Website" class="w-full h-48 sm:h-60 object-cover">
            <div class="p-4 sm:p-6">
                <h2 class="text-lg sm:text-xl font-bold text-white">About the Project</h2>
                <p class="mt-4 text-sm sm:text-base text-gray-300">
                    Portfol.io is a collaborative project designed to showcase the team's creativity and technical expertise. 
                    It features a responsive design, modern UI/UX, and a structured layout to highlight individual and team contributions.
                </p>
                <h3 class="text-base sm:text-lg font-bold text-white mt-6">Key Features</h3>
                <ul class="list-disc list-inside mt-4 text-sm sm:text-base text-gray-300">
                    <li>Responsive design for all devices</li>
                    <li>Showcase of team projects and individual contributions</li>
                    <li>Modern UI/UX with smooth transitions</li>
                    <li>Built using Svelte and Tailwind CSS</li>
                </ul>
                <h3 class="text-base sm:text-lg font-bold text-white mt-6">Technologies Used</h3>
                <ul class="list-disc list-inside mt-4 text-sm sm:text-base text-gray-300">
                    <li>Svelte for fast and efficient rendering</li>
                    <li>Tailwind CSS for consistent and modern styling</li>
                    <li>JavaScript for interactivity</li>
                </ul>
                <a
                    href="https://github.com/Brent001/Portfol.io.git"
                    target="_blank"
                    class="mt-6 inline-flex items-center bg-blue-600 hover:bg-blue-700 text-white font-semibold py-2 px-4 rounded-lg shadow-md transition duration-300"
                >
                    <svg
                        xmlns="http://www.w3.org/2000/svg"
                        class="w-5 h-5 mr-2"
                        fill="currentColor"
                        viewBox="0 0 24 24"
                    >
                        <path
                            d="M12 .297c-6.63 0-12 5.373-12 12 0 5.303 3.438 9.8 8.205 11.387.6.113.82-.258.82-.577v-2.234c-3.338.726-4.033-1.416-4.033-1.416-.546-1.387-1.333-1.757-1.333-1.757-1.089-.744.083-.729.083-.729 1.205.084 1.838 1.236 1.838 1.236 1.07 1.835 2.809 1.305 3.495.998.108-.775.418-1.305.762-1.605-2.665-.3-5.466-1.332-5.466-5.93 0-1.31.467-2.381 1.235-3.221-.123-.303-.535-1.523.117-3.176 0 0 1.008-.322 3.3 1.23.957-.266 1.983-.399 3.003-.404 1.02.005 2.047.138 3.006.404 2.29-1.552 3.297-1.23 3.297-1.23.653 1.653.241 2.873.118 3.176.77.84 1.233 1.911 1.233 3.221 0 4.61-2.807 5.625-5.479 5.921.43.372.823 1.102.823 2.222v3.293c0 .322.218.694.825.576 4.765-1.587 8.2-6.084 8.2-11.386 0-6.627-5.373-12-12-12z"
                        />
                    </svg>
                    View GitHub Repository
                </a>
            </div>
        </div>
    </section>
</main>

<Footer />