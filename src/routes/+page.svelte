<script>
	import '../app.css';
	import { onMount } from 'svelte';
	import Navbar from './components/Navbar.svelte';
	import Home from './components/Home.svelte';
	import About from './components/About.svelte';
	import Tools from './components/Tools.svelte';
	import Porto from './components/Porto.svelte';
	import Footer from './components/Footbar.svelte';
	
	import AOS from 'aos';
	import 'aos/dist/aos.css';
	
	let isButtonVisible = false;
  
	onMount(() => {
	  AOS.init({
		duration: 1000,
		once: true,
	  });
  
	  window.addEventListener('scroll', () => {
		if (window.scrollY > 100) {
		  isButtonVisible = true;
		} else {
		  isButtonVisible = false;
		}
	  });
	});
  
	function scrollToTop() {
	  window.scrollTo({ top: 0, behavior: 'smooth' });
	}
  </script>
  
  <style>
	html {
	  scroll-behavior: smooth;
	}
  
	body {
	  padding-top: 60px;
	}
  
	.scroll-to-top {
	  position: fixed;
	  bottom: 20px;
	  right: 20px;
	  color: white;
	  padding: 10px 15px;
	  border-radius: 50%;
	  box-shadow: 0 2px 5px rgba(0, 0, 0, 0.2);
	  cursor: pointer;
	  transition: opacity 0.3s;
	}
  
	.scroll-to-top:hover {
	  background-color: #357ABD;
	}
  </style>
  
  <Navbar />
  <section id="home">
	<Home />
  </section>
  <section id="porto">
	<Porto />
  </section>
  <section id="tools">
	<Tools />
  </section>
  <section id="contact">
	<Footer />
  </section>
  
  <!-- Scroll to Top Button -->
  {#if isButtonVisible}
	<button class="scroll-to-top bg-indigo-500" on:click={scrollToTop}>
	  &#8679;
	</button>
  {/if}
  