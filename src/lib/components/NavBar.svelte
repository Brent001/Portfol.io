<script>
  let isMenuOpen = false;

  function toggleMenu() {
    isMenuOpen = !isMenuOpen;
  }
</script>

<nav class="border-gray-700 bg-gray-800 text-white">
  <div class="max-w-screen-xl flex flex-wrap items-center justify-between mx-auto p-4">
    <a href="/" class="flex items-center space-x-3">
      <img src="/img/logo.png" class="h-8" alt="Group Logo" />
      <span class="self-center text-2xl font-bold whitespace-nowrap">Portfol.io</span>
    </a>
    <button 
      type="button" 
      class="inline-flex items-center p-2 w-10 h-10 justify-center text-sm text-gray-400 rounded-lg md:hidden hover:bg-gray-700 focus:outline-none focus:ring-2 focus:ring-gray-600" 
      aria-controls="navbar-solid-bg" 
      aria-expanded={isMenuOpen} 
      on:click={toggleMenu}
    >
      <span class="sr-only">Open main menu</span>
      <svg class="w-5 h-5" xmlns="http://www.w3.org/2000/svg" fill="none" viewBox="0 0 17 14" aria-hidden="true">
        <path stroke="currentColor" stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M1 1h15M1 7h15M1 13h15" />
      </svg>
    </button>
    <div 
      class={`w-full md:block md:w-auto transition-all duration-300 ease-in-out overflow-hidden ${
        isMenuOpen ? 'max-h-screen opacity-100' : 'max-h-0 opacity-0 md:opacity-100 md:max-h-full'
      }`} 
      id="navbar-solid-bg"
    >
      <ul class="flex flex-col font-medium mt-4 rounded-lg bg-gray-800 md:space-x-8 md:flex-row md:mt-0 md:border-0">
        <li>
          <a href="/about" class="block py-2 px-3 md:p-0 text-gray-300 hover:text-white">About Us</a>
        </li>
        <li>
          <a href="/projects" class="block py-2 px-3 md:p-0 text-gray-300 hover:text-white">Projects</a>
        </li>
        <li>
          <a href="/team" class="block py-2 px-3 md:p-0 text-gray-300 hover:text-white">Team</a>
        </li>
        <li>
          <a href="/contact" class="block py-2 px-3 md:p-0 text-gray-300 hover:text-white">Contact</a>
        </li>
      </ul>
    </div>
  </div>
</nav>
