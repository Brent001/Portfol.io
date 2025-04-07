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
        About Living in IT Era
    </h1>
    <section class="max-w-lg text-sm leading-relaxed sm:max-w-3xl sm:text-base">
        <p class="mb-6" transition:fade={{ duration: 300 }}>
            Welcome to <strong>Living in IT Era</strong>, a project dedicated to exploring the transformative impact of technology on our daily lives. 
            In this fast-paced digital age, technology has become an integral part of how we work, communicate, and live.
        </p>
        <p class="mb-6" transition:fade={{ duration: 300 }}>
            Our mission is to provide insights into the latest trends in information technology, highlight its influence on various industries, 
            and discuss how individuals and organizations can adapt to thrive in this ever-evolving landscape.
        </p>
        <p class="mb-6" transition:fade={{ duration: 300 }}>
            From artificial intelligence and cloud computing to cybersecurity and digital transformation, we aim to cover a wide range of topics 
            that shape the IT era. Whether you're a tech enthusiast, a professional, or someone curious about the role of technology in modern society, 
            this project is for you.
        </p>
        <p class="mb-6" transition:fade={{ duration: 300 }}>
            Join us as we navigate the opportunities and challenges of living in the IT era, and discover how technology can empower us to achieve 
            more and connect in meaningful ways.
        </p>
    </section>
</main>

<Footer />