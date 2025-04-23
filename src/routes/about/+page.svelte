<script>
    import { fade } from 'svelte/transition'; // Import the fade transition
    import Footer from '$lib/components/Footer.svelte';
    import NavBar from '../../lib/components/NavBar.svelte';
</script>

<svelte:head>
    <meta name="viewport" content="width=device-width, initial-scale=1.0" />
</svelte:head>

<NavBar />

<div class="flex flex-col min-h-screen bg-gray-900 text-white">
    <main class="flex-grow flex flex-col items-center px-4 py-8 sm:px-6 sm:py-12">
        <h1 class="text-2xl font-extrabold mb-6 text-center sm:text-3xl">
            About Portfol.io
        </h1>
        <section class="max-w-lg text-sm leading-relaxed sm:max-w-3xl sm:text-base">
            <div in:fade={{ duration: 300 }}>
                <p class="mb-6">
                    <strong>Portfol.io</strong> is a modern and responsive platform designed to showcase the creativity, skills, and achievements of individuals and teams. 
                    Built with cutting-edge technologies like <strong>Svelte</strong> and <strong>Tailwind CSS</strong>, Portfol.io ensures a seamless and visually captivating experience for users.
                </p>
            </div>
            <div in:fade={{ duration: 300 }}>
                <p class="mb-6">
                    Our mission is to empower creators, professionals, and teams to present their work in a way that truly stands out. Whether you're a developer, designer, entrepreneur, or artist, 
                    Portfol.io provides the tools you need to craft a portfolio that reflects your unique identity and vision.
                </p>
            </div>
            <div in:fade={{ duration: 300 }}>
                <p class="mb-6">
                    The platform was developed by a passionate team of BS-Tourism students, including <strong>Brent Kenneth Abrazaldo</strong>, <strong>Irish Villanueva</strong>, and <strong>Shaira Embornal</strong>. 
                    Each team member brought their unique skills and creativity to the project, ensuring that Portfol.io is not just functional but also inspiring.
                </p>
            </div>
            <div in:fade={{ duration: 300 }}>
                <p class="mb-6">
                    With features like fully customizable layouts, responsive design, and intuitive navigation, Portfol.io ensures your portfolio leaves a lasting impression. 
                    Share your story, highlight your achievements, and connect with opportunities that align with your goals—all in one place.
                </p>
            </div>
            <div in:fade={{ duration: 300 }}>
                <p class="mb-6">
                    Technologies used in building Portfol.io include:
                </p>
            </div>
            <ul class="list-disc list-inside mb-6 text-sm sm:text-base">
                <li>Svelte for fast and efficient rendering</li>
                <li>Tailwind CSS for consistent and modern styling</li>
                <li>JavaScript for interactivity</li>
            </ul>
        </section>
    </main>
</div>

<footer class="bg-gray-800 text-gray-400 py-1 text-center">
    <Footer />
</footer>
