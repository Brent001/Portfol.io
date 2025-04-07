<script>
    import { fade } from 'svelte/transition'; // Import the fade transition
    import Footer from '$lib/components/Footer.svelte';
    import NavBar from '../../lib/components/NavBar.svelte';
</script>

<!-- Add meta tag for viewport -->
<svelte:head>
    <meta name="viewport" content="width=device-width, initial-scale=1.0" />
</svelte:head>

<NavBar />

<main class="flex flex-col items-center px-4 py-8 min-h-screen bg-gray-900 text-white sm:px-6 sm:py-12">
    <h1 class="text-2xl font-extrabold mb-6 text-center sm:text-3xl">
        About Portfol.io
    </h1>
    <section class="max-w-lg text-sm leading-relaxed sm:max-w-3xl sm:text-base">
        <p class="mb-6" transition:fade={{ duration: 300 }}>
            <strong>Portfol.io</strong> is more than just a platform—it's your gateway to showcasing your talent, creativity, and professional journey. 
            Designed with innovation and simplicity in mind, Portfol.io empowers individuals, teams, and organizations to present their work in a way that truly stands out.
        </p>
        <p class="mb-6" transition:fade={{ duration: 300 }}>
            Our mission is to provide a seamless and visually captivating experience for creators and professionals. Whether you're a developer, designer, entrepreneur, or artist, 
            Portfol.io offers the tools you need to craft a portfolio that reflects your unique identity and vision.
        </p>
        <p class="mb-6" transition:fade={{ duration: 300 }}>
            With features like fully customizable layouts, responsive design, and intuitive navigation, Portfol.io ensures your portfolio leaves a lasting impression. 
            Share your story, highlight your achievements, and connect with opportunities that align with your goals—all in one place.
        </p>
        <p class="mb-6" transition:fade={{ duration: 300 }}>
            Join the growing community of innovators and professionals who trust Portfol.io to elevate their online presence. 
            Take the first step toward building a portfolio that not only showcases your work but also inspires and engages your audience.
        </p>
    </section>
</main>

<Footer />