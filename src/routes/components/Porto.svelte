<script>
  import { onMount } from 'svelte';
  import Image1 from '../../lib/images/gyroskop.png';
  import Image2 from '../../lib/images/blkpp.png';
  import Image3 from '../../lib/images/book-data.png';
  import Image4 from '../../lib/images/ocean-calc.png';
  import Image5 from '../../lib/images/mobile-travel.png';
  

  let projects = [
    { id: 1, image: Image1, title: 'Company Profile Madana',shortDescription:'VueJS, Bootstrap, Laravel, ChartJS', description: 'Mengembangkan dashboard institusi balai latihan kerja dan pengembangan produktivitas dengan memanfaatkan integrasi api terhadap filter data dan pembuatan chart berbasis chart.js' },
    { id: 2, image: Image2, title: 'Gyroskop',shortDescription:'Phpmyadmin, Native Javascript', description: 'Mengembangkan website pembelian tiket online dengan integrasi phpmyadmin sebagai database lokal' },
    { id: 3, image: Image3, title: 'Book Library',shortDescription:'Laravel, Bootstrap', description: 'Mengembangkan website penyimpanan data buku dengan penerapan create, read, update, dan delete pada laravel' },
    { id: 4, image: Image4, title: 'Ocean Calculator',shortDescription:'Native Javascript, Vanilla CSS', description: 'Mengembangkan website perhitungan total sampah pertahun secara real time dengan javascript native' },
    { id: 5, image: Image5, title: 'KUR Jogja',shortDescription:'Kotlin, Firebase', description: 'Mengembangkan aplikasi android pemesanan kereta secara online dengan penerapan google firebase sebagai cloud database' },
    { id: 6, image: Image1, title: 'Company Profile Madana',shortDescription:'VueJS, Bootstrap, Laravel, ChartJS', description: 'Mengembangkan dashboard institusi balai latihan kerja dan pengembangan produktivitas dengan memanfaatkan integrasi api terhadap filter data dan pembuatan chart berbasis chart.js' },
    { id: 7, image: Image4, title: 'KUR Jogja',shortDescription:'VueJS & Laravel', description: 'This is a longer description for Project 6.' },
  ];

  let showMore = false;

  const toggleShowMore = () => {
    showMore = !showMore;
  };
</script>

<style>
  .card {
    position: relative;
    overflow: hidden;
    transition: transform 0.3s ease;
  }
  
  .card:hover .description {
    opacity: 1;
    transform: translateY(0);
  }

  .description {
    position: absolute;
    bottom: 0;
    left: 0;
    right: 0;
    background: rgba(0, 0, 0, 0.7);
    color: white;
    padding: 80px;
    transition: opacity 0.3s ease, transform 0.3s ease;
    opacity: 0;
    transform: translateY(100%);
    height: 100%;
    display: flex;
    align-items: center;
    justify-content: center;
    text-align: center;
  }
</style>

<div class="bg-indigo-500">
  <div class="container mx-auto py-8">
    <h1 class="text-3xl lg:text-4xl font-bold pb-10 text-white text-center break-words overflow-hidden w-full lg:w-auto lg:pb-10 pt-4" data-aos="fade-up">
      My Recent Portofolio
    </h1>
    <div class="grid grid-cols-1 sm:grid-cols-2 lg:grid-cols-3 gap-10 p-10 lg:p-0">
      {#each (showMore ? projects : projects.slice(0, 6)) as project (project.id)}
        <div class="card bg-white rounded-lg shadow-lg overflow-hidden" data-aos="zoom-in">
          <img src={project.image} alt={project.title} class="w-full object-cover" />
          <div class="p-10 text-center">
            <h3 class="text-lg font-semibold mb-2">{project.title}</h3>
            <h3>{project.shortDescription}</h3>
            <div class="description">{project.description}</div>
          </div>
        </div>
      {/each}
    </div>
    <!-- Uncomment this section if you want to include the "See More" button -->
    <!-- {#if projects.length > 5}
      <button on:click={toggleShowMore} class="mt-4 px-4 py-2 bg-blue-500 text-white rounded-lg">
        {showMore ? 'See Less' : 'See More'}
      </button>
    {/if} -->
  </div>
</div>
