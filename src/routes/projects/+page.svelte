<script>
    import Footer from '$lib/components/Footer.svelte';
    import NavBar from '../../lib/components/NavBar.svelte';
    import { scale } from 'svelte/transition'; // Import scale transition
</script>

<NavBar />

<main class="flex-grow py-12 px-6 sm:px-12 bg-gray-900 text-gray-100">
    <!-- Hero Section -->
    <section class="max-w-screen-lg mx-auto text-center">
        <div class="flex justify-center mb-6">
            <img src="/img/logo.png" alt="Portfol.io Logo" class="h-14 sm:h-16 object-contain" />
        </div>
        <h1 class="text-3xl sm:text-4xl font-extrabold text-white">
            Our Team Projects
        </h1>
        <p class="mt-4 text-base sm:text-lg text-gray-300">
            Explore the collaborative projects created by our talented team. Each project reflects our dedication, creativity, and teamwork.
        </p>
    </section>

    <!-- Team Projects Showcase Section -->
    <section class="mt-12 grid grid-cols-1 gap-6 sm:grid-cols-2 lg:grid-cols-3 max-w-screen-lg mx-auto">
        <!-- Team Project 1: Portfol.io Website -->
        <div class="bg-gray-800 rounded-lg shadow-lg overflow-hidden transform hover:scale-105 transition duration-300" in:scale={{ duration: 400, start: 0.9 }} out:scale={{ duration: 300, start: 1 }}>
            <img src="/img/projects/portfol.io.png" alt="Portfol.io Website" class="w-full h-40 sm:h-48 object-cover">
            <div class="p-4 sm:p-6">
                <h2 class="text-lg sm:text-xl font-bold text-white">Portfol.io Website</h2>
                <p class="mt-2 text-sm sm:text-base text-gray-400">
                    A modern and responsive portfolio website showcasing our team's projects, skills, and creativity.
                </p>
                <a href="/projects/portfol.io" class="mt-4 inline-block text-blue-400 hover:underline">
                    View Details →
                </a>
            </div>
        </div>

        <!-- Team Project 2: Placeholder -->
        <div class="bg-gray-800 rounded-lg shadow-lg overflow-hidden transform hover:scale-105 transition duration-300" in:scale={{ duration: 400, start: 0.9 }} out:scale={{ duration: 300, start: 1 }}>
            <img src="/img/projects/place-holder.webp" alt="Upcoming Project" class="w-full h-40 sm:h-48 object-cover">
            <div class="p-4 sm:p-6">
                <h2 class="text-lg sm:text-xl font-bold text-white">Upcoming Project</h2>
                <p class="mt-2 text-sm sm:text-base text-gray-400">
                    This project is currently under development. Stay tuned for updates!
                </p>
            </div>
        </div>

        <!-- Team Project 3: Placeholder -->
        <div class="bg-gray-800 rounded-lg shadow-lg overflow-hidden transform hover:scale-105 transition duration-300" in:scale={{ duration: 400, start: 0.9 }} out:scale={{ duration: 300, start: 1 }}>
            <img src="/img/projects/place-holder.webp" alt="Upcoming Project" class="w-full h-40 sm:h-48 object-cover">
            <div class="p-4 sm:p-6">
                <h2 class="text-lg sm:text-xl font-bold text-white">Upcoming Project</h2>
                <p class="mt-2 text-sm sm:text-base text-gray-400">
                    This project is currently under development. Stay tuned for updates!
                </p>
            </div>
        </div>
    </section>
</main>

<Footer />