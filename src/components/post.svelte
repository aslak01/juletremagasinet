<script> 
  export let product
  let shipping = 80
  let vipps = product.meta_data.filter(i => i.key === "_vipps_shareable_links")[0].value
  
  $: console.log(vipps)
  
  let selections = {
    tab: 'desc'
  }
</script>


<section class="text-gray-600 body-font max-w-screen-xl mx-auto">
  <div class="container px-5 py-12 mx-auto flex flex-wrap">
    <div class="lg:w-1/2 w-full mb-10 lg:mb-0 rounded overflow-hidden">
      <img alt="{product.images[0].alt}" class="object-cover object-center h-full w-full" src="{product.images[0].src}">
    </div>
    <div class="container flex flex-col flex-wrap -mb-10 lg:w-1/2 lg:pl-12 text-left">
 
      
      <div class="mx-auto my-auto w-full md:w-3/4 lg:w-full max-w-full">
        <div class="flex flex-wrap">
          <div class="w-full mb-6 lg:mb-0">
            <h2 class="text-sm title-font text-gray-500 tracking-widest">Norsk Juletresertifiseringsinstitutt</h2>
            <h1 class="text-gray-900 text-3xl title-font font-medium mb-4">{product.name}</h1>
            <!-- <img alt="juletrær" class="w-full h-auto object-cover object-center rounded" src="juletre2.jpg"> -->
            <div class="border-b border-gray-200">
              <div class="flex mb-4">
                <a href="/" class="flex-grow text-indigo-500 border-b-2 border-indigo-500 py-2 text-lg px-1">Beskrivelse</a>
                <a href="/" class="flex-grow border-b-2 border-gray-300 py-2 text-lg px-1">Reviews</a>
                <a href="/" class="flex-grow border-b-2 border-gray-300 py-2 text-lg px-1">Details</a>
              </div>
              <p class="leading-relaxed mb-4">{@html product.description}</p>
            </div>
            <div class="container flex">
              <div class="w-full mr-5 max-h-full">
                <img src="{product.images[0].src}" alt="{product.images[0].alt}" class="max-h-full" />
              </div>
              <div class="w-full ml-auto">
                <div class="flex py-2">
                  <span class="text-gray-500">Utgis</span>
                  <span class="ml-auto text-gray-900">Årlig</span>
                </div>
                <div class="flex border-t border-gray-200 py-2">
                  <span class="text-gray-500">Pris</span>
                  <span class="ml-auto text-gray-900">kr {product.price}</span>
                </div>
                <div class="flex border-t border-b mb-6 border-gray-200 py-2">
                  <span class="text-gray-500">Frakt</span>
                  <span class="ml-auto text-gray-900">kr {shipping}</span>
                </div>
                <div class="flex border-t border-b mb-6 border-gray-200 py-2">
                  <span class="text-gray-700">Total</span>
                  <span class="ml-auto title-font font-medium text-gray-900">kr {parseInt(product.price) + shipping}</span>
                </div>
  
            </div>

            </div>
            <div class="flex">
              <div class="flex ml-auto">
                {#if vipps.url}
                <a href="{vipps.url}"><img alt="vipps hurtigkasse" src="hurtigkasse.svg" /></a>
                {/if}
                <!-- <button class="flex ml-auto text-white bg-yellow-500 border-0 py-2 px-6 focus:outline-none hover:bg-yellow-600 rounded">Vipps hurtigkasse</button>
                <button class="flex ml-2 text-white bg-yellow-500 border-0 py-2 px-6 focus:outline-none hover:bg-yellow-600 rounded">Vipps abonnement</button> -->
              </div>
            </div>
          </div>
        </div>
      </div>

      <!-- <div class="flex flex-col mb-10 lg:items-start items-center">
        <div class="w-12 h-12 inline-flex items-center justify-center rounded-full bg-indigo-100 text-indigo-500 mb-5">
          <svg fill="none" stroke="currentColor" stroke-linecap="round" stroke-linejoin="round" stroke-width="2" class="w-6 h-6" viewBox="0 0 24 24">
            <path d="M22 12h-4l-3 9L9 3l-3 9H2"></path>
          </svg>
        </div>
        <div class="flex-grow">
          <h2 class="text-gray-900 text-lg title-font font-medium mb-3">Shooting Stars</h2>
          <p class="leading-relaxed text-base">Blue bottle crucifix vinyl post-ironic four dollar toast vegan taxidermy. Gastropub indxgo juice poutine.</p>
          <a class="mt-3 text-indigo-500 inline-flex items-center">Learn More
            <svg fill="none" stroke="currentColor" stroke-linecap="round" stroke-linejoin="round" stroke-width="2" class="w-4 h-4 ml-2" viewBox="0 0 24 24">
              <path d="M5 12h14M12 5l7 7-7 7"></path>
            </svg>
          </a>
        </div>
      </div> -->
      <!-- <div class="flex flex-col mb-10 lg:items-start items-center">
        <div class="w-12 h-12 inline-flex items-center justify-center rounded-full bg-indigo-100 text-indigo-500 mb-5">
          <svg fill="none" stroke="currentColor" stroke-linecap="round" stroke-linejoin="round" stroke-width="2" class="w-6 h-6" viewBox="0 0 24 24">
            <circle cx="6" cy="6" r="3"></circle>
            <circle cx="6" cy="18" r="3"></circle>
            <path d="M20 4L8.12 15.88M14.47 14.48L20 20M8.12 8.12L12 12"></path>
          </svg>
        </div>
        <div class="flex-grow">
          <h2 class="text-gray-900 text-lg title-font font-medium mb-3">The Catalyzer</h2>
          <p class="leading-relaxed text-base">Blue bottle crucifix vinyl post-ironic four dollar toast vegan taxidermy. Gastropub indxgo juice poutine.</p>
          <a class="mt-3 text-indigo-500 inline-flex items-center">Learn More
            <svg fill="none" stroke="currentColor" stroke-linecap="round" stroke-linejoin="round" stroke-width="2" class="w-4 h-4 ml-2" viewBox="0 0 24 24">
              <path d="M5 12h14M12 5l7 7-7 7"></path>
            </svg>
          </a>
        </div>
      </div>
      <div class="flex flex-col mb-10 lg:items-start items-center">
        <div class="w-12 h-12 inline-flex items-center justify-center rounded-full bg-indigo-100 text-indigo-500 mb-5">
          <svg fill="none" stroke="currentColor" stroke-linecap="round" stroke-linejoin="round" stroke-width="2" class="w-6 h-6" viewBox="0 0 24 24">
            <path d="M20 21v-2a4 4 0 00-4-4H8a4 4 0 00-4 4v2"></path>
            <circle cx="12" cy="7" r="4"></circle>
          </svg>
        </div>
        <div class="flex-grow">
          <h2 class="text-gray-900 text-lg title-font font-medium mb-3">Neptune</h2>
          <p class="leading-relaxed text-base">Blue bottle crucifix vinyl post-ironic four dollar toast vegan taxidermy. Gastropub indxgo juice poutine.</p>
          <a class="mt-3 text-indigo-500 inline-flex items-center">Learn More
            <svg fill="none" stroke="currentColor" stroke-linecap="round" stroke-linejoin="round" stroke-width="2" class="w-4 h-4 ml-2" viewBox="0 0 24 24">
              <path d="M5 12h14M12 5l7 7-7 7"></path>
            </svg>
          </a>
        </div>
      </div> -->
    </div>
  </div>
</section>