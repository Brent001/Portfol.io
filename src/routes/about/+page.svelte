<script>
    import { fade } from 'svelte/transition';
    import Footer from '$lib/components/Footer.svelte';
    import NavBar from '../../lib/components/NavBar.svelte';
</script>

<svelte:head>
    <meta name="viewport" content="width=device-width, initial-scale=1.0" />
</svelte:head>

<div class="flex flex-col min-h-screen">
    <NavBar />

    <main class="flex-grow px-4 py-8 bg-gray-900 text-white sm:px-6 sm:py-12">
        <div class="max-w-4xl mx-auto"> <!-- Added container for better content alignment -->
            <h1 class="text-2xl font-extrabold mb-6 text-center sm:text-3xl">
                About Portfol.io
            </h1>
            <section class="max-w-lg text-sm leading-relaxed sm:max-w-3xl sm:text-base">
                <p class="mb-6" transition:fade={{ duration: 300 }}>
                    <strong>Portfol.io</strong> is a modern and responsive platform designed to showcase the creativity, skills, and achievements of individuals and teams. 
                    Built with cutting-edge technologies like <strong>Svelte</strong> and <strong>Tailwind CSS</strong>, Portfol.io ensures a seamless and visually captivating experience for users.
                </p>
                <p class="mb-6" transition:fade={{ duration: 300 }}>
                    Our mission is to empower creators, professionals, and teams to present their work in a way that truly stands out. Whether you're a developer, designer, entrepreneur, or artist, 
                    Portfol.io provides the tools you need to craft a portfolio that reflects your unique identity and vision.
                </p>
                <p class="mb-6" transition:fade={{ duration: 300 }}>
                    The platform was developed by a passionate team of BS-Tourism students, including <strong>Brent Kenneth Abrazaldo</strong>, <strong>Irish Villanueva</strong>, and <strong>Shaira Embornal</strong>. 
                    Each team member brought their unique skills and creativity to the project, ensuring that Portfol.io is not just functional but also inspiring.
                </p>
                <p class="mb-6" transition:fade={{ duration: 300 }}>
                    With features like fully customizable layouts, responsive design, and intuitive navigation, Portfol.io ensures your portfolio leaves a lasting impression. 
                    Share your story, highlight your achievements, and connect with opportunities that align with your goals—all in one place.
                </p>
                <p class="mb-6" transition:fade={{ duration: 300 }}>
                    Technologies used in building Portfol.io include:
                </p>
                <ul class="list-disc list-inside mb-6 text-sm sm:text-base text-gray-300">
                    <li>Svelte for fast and efficient rendering</li>
                    <li>Tailwind CSS for consistent and modern styling</li>
                    <li>JavaScript for interactivity</li>
                </ul>
                <p class="mb-6" transition:fade={{ duration: 300 }}>
                    Join the growing community of innovators and professionals who trust Portfol.io to elevate their online presence. 
                    Take the first step toward building a portfolio that not only showcases your work but also inspires and engages your audience.
                </p>
            </section>
        </div>
    </main>

    <Footer />
</div>