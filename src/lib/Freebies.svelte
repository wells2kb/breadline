<script>
  import { site_data } from '$lib/SiteData.js'
</script>

{#each site_data.freebies as freebie}
  <div class="relative h-95 w-75 flex flex-col items-center">
    <img class="rounded-lg object-cover h-full w-full object-contain" src="{freebie.image}"/>
    <h2 class="absolute w-full top-5 font-bold backdrop-blur-xl text-center text-white tracking-[0.05em] text-shadow-lg/30">{freebie.name}</h2>
    <div class="absolute top-1 right-1 metallic shadow-xl/50 rounded-full">
      <h3 class="px-2 text-center font-medium items-center">{freebie.quantity}</h3>
    </div>
    <div class="absolute backdrop-blur-xl bottom-8.5 h-8 w-full px-2">
      <h2 class="font-semibold text-center text-white text-shadow-lg">{site_data.companies[freebie.company].name}</h2>
    </div>
    <div class="absolute metallic shadow-xl/40 rounded-full bottom-2 w-[90%] px-2">
      <div class="h-8 flex flex-row justify-around">
        <div class="flex flex-row items-center justify-center w-full">
          <img class="p-1 h-full" src="./walking.png"/>
          <p class="font-medium">{Math.floor(Math.random() * 20)}</p>
        </div>
        <div class="flex flex-row items-center justify-center w-full">
          <img class="p-1 h-full" src="https://svgsilh.com/svg/34451.svg"/>
          <p class="font-medium">{Math.floor(Math.random() * 20)}</p>
        </div>
        <div class="flex flex-row items-center justify-center w-full">
          <img class="p-1 h-full" src="./bus_and_train.png"/>
          <p class="font-medium">{Math.floor(Math.random() * 20)}</p>
        </div>
        <div class="flex flex-row items-center justify-center w-full">
          <img class="p-1 h-full" src="./car.png"/>
          <p class="font-medium">{Math.floor(Math.random() * 25)}</p>
        </div>
      </div>
    </div>
  </div>
{/each}
