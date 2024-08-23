<script>
  let isMenuOpen = false;

  function toggleMenu() {
    isMenuOpen = !isMenuOpen;
  }
</script>

<style>
  @import "tailwindcss/tailwind.css";
</style>

<nav class="bg-white shadow-lg">
  <div class="container mx-auto">
    <div class="flex justify-between mx-6 xl:mx-0">

      <!-- Logo Section -->
      <div class="flex space-x-4">
        <a href="#" class="flex items-center lg:py-10 py-8 text-gray-700">
          <span class="font-bold">ERLANGGA</span>
        </a>
      </div>

      <!-- Primary Navbar items -->
      <div class="hidden md:flex items-center space-x-1">
        <a href="#" class="py-5 px-3 text-gray-700 hover:text-gray-900">Home</a>
        <a href="#" class="py-5 px-3 text-gray-700 hover:text-gray-900">About</a>
        <a href="#" class="py-5 px-3 text-gray-700 hover:text-gray-900">Projects</a>
      </div>

      <!-- Contact Me Button -->
      <div class="hidden md:flex items-center">
        <a href="#" class="py-2 px-3 bg-indigo-600 text-white rounded hover:bg-indigo-500 transition duration-300">Contact</a>
      </div>

      <!-- Mobile Menu Button -->
      <div class="md:hidden flex items-center">
        <button on:click={toggleMenu}>
          <svg class="w-6 h-6" xmlns="http://www.w3.org/2000/svg" fill="none" viewBox="0 0 24 24" stroke="currentColor">
            <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M4 6h16M4 12h16m-7 6h7" />
          </svg>
        </button>
      </div>

    </div>
  </div>

  <!-- Mobile Menu -->
  {#if isMenuOpen}
    <div class="md:hidden mx-3 pb-8 px-4">
      <a href="#" class="block py-2 text-sm text-gray-700">Home</a>
      <a href="#" class="block py-2 text-sm text-gray-700">About</a>
      <a href="#" class="block py-2 text-sm text-gray-700">Projects</a>
      <a href="#" class="block py-2 mt-4 text-sm text-center text-gray-700 bg-indigo-600 text-white rounded">Contact Me</a>
    </div>
  {/if}
</nav>