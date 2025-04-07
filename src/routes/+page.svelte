<script>
    import NavBar from '../lib/components/NavBar.svelte';
    import Footer from '../lib/components/Footer.svelte'; // Import the Footer component
</script>

<NavBar />

<main class="flex-grow">
    <!-- Hero Section -->
    <section id="hero" class="text-center py-20 bg-gray-800 text-white">
      <div class="max-w-screen-lg mx-auto">
        <h1 class="text-4xl font-bold mb-4">Welcome to Our Portfolio</h1>
        <p class="text-lg mb-6">
          We are a team of passionate developers creating innovative and impactful projects.
        </p>
        <a href="/team" class="bg-blue-500 hover:bg-blue-600 text-white py-2 px-6 rounded-lg">
          Meet Our Team
        </a>
      </div>
    </section>
  
    <!-- Team Section -->
    <section id="team" class="py-16 px-8 bg-gray-900 text-gray-100">
      <div class="max-w-screen-lg mx-auto">
        <h2 class="text-3xl font-bold mb-6">Meet the Team</h2>
        <div class="grid grid-cols-1 md:grid-cols-2 lg:grid-cols-3 gap-6">
          <div class="text-center">
            <img src="/img/img1.jpg" alt="Team Member" class="rounded-xl mx-auto mb-3 w-130 h-120 object-cover">
            <h3 class="text-xl font-semibold">Irish M. Villanueva</h3>
            <p class="text-sm">BS-Tourism</p>
          </div>
          <div class="text-center">
            <img src="/img/img3.jpg" alt="Team Member" class="rounded-xl mx-auto mb-3 w-130 h-120 object-cover">
            <h3 class="text-xl font-semibold">Brent Kenneth O. Abrazaldo</h3>
            <p class="text-sm">BS-Computer Science</p>
          </div>
          <div class="text-center">
            <img src="/img/img2.jpg" alt="Team Member" class="rounded-xl mx-auto mb-3 w-130 h-120 object-cover">
            <h3 class="text-xl font-semibold">Shaira Embornal</h3>
            <p class="text-sm">BS-Tourism</p>
          </div>
        </div>
      </div>
    </section>
  </main>
  
  <Footer />
