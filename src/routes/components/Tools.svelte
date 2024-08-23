<script>
    import LaravelIcon from '../../lib/images/laravel-icon.png';
    let cards = [
      { id: 1, title: 'HTML', type: 'mobile', image: LaravelIcon },
      { id: 2, title: 'CSS', type: 'web', image: LaravelIcon },
      { id: 3, title: 'JavaScript', type: 'mobile', image: LaravelIcon },
      { id: 4, title: 'Bootstrap', type: 'web', image: LaravelIcon },
      { id: 5, title: 'VSCode', type: 'Tools', image: LaravelIcon },
      { id: 6, title: 'Atom', type: 'Tools', image: LaravelIcon },
      { id: 7, title: 'Github', type: 'mobile', image: LaravelIcon },
      { id: 8, title: 'VueJS', type: 'Framework', image: LaravelIcon },
      { id: 9, title: 'Laravel', type: 'Framework', image: LaravelIcon },
      { id: 10, title: 'Postman', type: 'web', image: LaravelIcon },
      { id: 11, title: 'Tool 11', type: 'Framework', image: LaravelIcon },
      { id: 12, title: 'Tool 12', type: 'Framework', image: LaravelIcon },
    ];
  </script>
  
  <style>
    @media (max-width: 640px) {
      .card-title {
        font-size: 0.875rem; 
      }
      .card-type {
        font-size: 0.75rem; 
      }
      .card-image {
        height: 4rem;
      }
    }
  </style>
  
  <div class="bg-gray-100">
    <div class="container mx-auto px-4 py-20">
      <h1 class="text-3xl lg:text-4xl font-bold pb-10 text-black text-center break-words overflow-hidden w-full lg:w-auto lg:pb-20 pt-4" data-aos="fade-up">
        Skill and Tools
      </h1>
      <div class="grid grid-cols-1 grid-cols-2 lg:grid-cols-6 gap-4 mb-12">
        {#each cards as card (card.id)}
          <div class="bg-white p-3 shadow-md flex items-center" data-aos="zoom-in">
            <img src={card.image} alt={card.title} class="card-image lg:h-20 p-3 object-cover mr-4"/>
            <div class="flex flex-col justify-between">
              <h3 class="card-title text-lg lg:text-xl font-bold">{card.title}</h3>
              <span class="card-type text-sm text-gray-600 capitalize">{card.type}</span>
            </div>
          </div>
        {/each}
      </div>
    </div>
  </div>
  