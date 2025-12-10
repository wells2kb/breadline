<script>
  import { site_data } from '$lib/SiteData.js'
  import Freebie from '$lib/Freebie.svelte'
  import TravelTimes from '$lib/TravelTimes.svelte'

  let pre_pop_up = null;
  let pop_up = null;

</script>

<div class="grid grid-cols-3 gap-5 w-fit mx-auto mb-20">
  {#each site_data.freebies as freebie}
    <Freebie class="h-95 w-75" data={freebie} onclick={
      () => {
        pop_up = freebie
        document.body.classList.add('lock-scroll')
      }
    }/>
  {/each}
</div>

{#if pop_up}
  <div class="fixed inset-0 flex items-center justify-center bg-black/40 backdrop-blur-[2px] z-9999">
    <div class="relative h-155 max-w-155 z-99999">
      <Freebie data={pop_up} class="w-full h-full" hide_footer={true}/>
      <div class="absolute -bottom-4 -right-4 metallic h-30 w-30 rounded-full flex justify-center items-center shadow-md/50 hover:scale-105 duration-105"
        onclick={() => alert("Not implmented")}
      >
        <div class="bg-white h-22 w-22 inset-shadow-sm/50 rounded-full flex justify-center items-center text-center">
          <p>Add to Order</p>
        </div>
      </div>
    </div>
    <div class="relative h-150 w-100 bg-white rounded-r-xl">
      <div class="h-full overflow-scroll flex flex-col items-center px-5 gap-5">
        <h2 class="text-center text-3xl mt-10">{site_data.companies[pop_up.company].name}</h2>
        <TravelTimes class="w-full"/>
        <p class="">{pop_up.description}</p>
        <h2 class="text-center text-3xl mt-10">While You're There</h2>
        <div class="grid col-1 gap-5 mx-10">
          {#each site_data.freebies.filter((x) => x.company == pop_up.company && x != pop_up) as other}
            <Freebie class="h-70 w-70" data={other} hide_footer={true} onclick={
              (event) => {
                pre_pop_up = pop_up
                pop_up = other
                event.currentTarget.parentElement.parentElement.scrollTop = 0;
              }
            }/>
          {/each}
        </div>
      </div>
      <div class="absolute -top-5 right-4 p-2 backdrop-blur-xl shadow-md/30 rounded-2xl flex justify-center hover:scale-105 duration-150"
        onclick={
          () => {
            pop_up = null
            pre_pop_up = null
            document.body.classList.remove('lock-scroll')
          }
      }>
        <img class="h-8 drop-shadow-md/60" src="./x.png"/>
      </div>
    </div>
  </div>
{/if}

<style>

</style>
