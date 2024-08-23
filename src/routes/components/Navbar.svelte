<script>
  let isMenuOpen = false;

  function toggleMenu() {
    isMenuOpen = !isMenuOpen;
  }

  function smoothScroll(event) {
    event.preventDefault();
    const targetId = event.currentTarget.getAttribute("href").substring(1);
    const targetElement = document.getElementById(targetId);
    if (targetElement) {
      window.scrollTo({
        top: targetElement.offsetTop, // Adjust the offset based on your navbar height
        behavior: "smooth",
      });
    }
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
        <a href="#home" class="flex items-center lg:py-10 py-8 text-gray-700">
          <span class="font-bold">ERLANGGA</span>
        </a>
      </div>

      <!-- Primary Navbar items -->
      <div class="hidden md:flex items-center space-x-1">
        <a href="#home" class="py-5 px-3 text-gray-700 hover:text-gray-900" on:click={smoothScroll}>Home</a>
        <a href="#porto" class="py-5 px-3 text-gray-700 hover:text-gray-900" on:click={smoothScroll}>Projects</a>
        <a href="#tools" class="py-5 px-3 text-gray-700 hover:text-gray-900" on:click={smoothScroll}>Tools</a>
      </div>

      <!-- Contact Me Button -->
      <div class="hidden md:flex items-center">
        <a href="#contact" class="py-2 px-3 bg-indigo-600 text-white rounded hover:bg-indigo-500 transition duration-300" on:click={smoothScroll}>Contact</a>
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
      <a href="#home" class="block py-2 text-sm text-gray-700" on:click={smoothScroll}>Home</a>
      <a href="#porto" class="block py-2 text-sm text-gray-700" on:click={smoothScroll}>Projects</a>
      <a href="#tools" class="block py-2 text-sm text-gray-700" on:click={smoothScroll}>Tools</a>
      <a href="#contact" class="block py-2 mt-4 text-sm text-center text-gray-700 bg-indigo-600 text-white rounded" on:click={smoothScroll}>Contact Me</a>
    </div>
  {/if}
</nav>
