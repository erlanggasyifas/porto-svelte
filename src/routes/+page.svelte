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
	
	onMount(() => {
	  AOS.init({
		duration: 1000, // duration of animation
		once: true, // whether animation should happen only once
	  });
	});
  </script>
  
  <Navbar />
  <Home />
  <Porto />
  <Tools />
  <Footer />
  