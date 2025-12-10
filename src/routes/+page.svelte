<script>
  import Freebies from "$lib/Freebies.svelte"
  import { site_data } from '$lib/SiteData.js'
  import Freebie from '$lib/Freebie.svelte'

  let there_is_no_way_to_extract_out_a_pop_up = false
  let company = null
</script>

<div class="h-18 mb-5">
  <div class="fixed w-full h-18 z-999 bg-gray-400/10 backdrop-blur-xl">
    <img class="absolute top-0 left-13 h-15 z-999 drop-shadow-md/50" src="./logo.png"/>
    <div class="absolute right-18 z-999 flex drop-shadow-md/30">
      {#if company}
        <h1 class="text-5xl mt-1 z-999">{site_data.companies[company].name}</h1>
      {:else}
        <img class="h-14 mt-1 hover:scale-105" src="./cart.png" onclick={() => alert("Not implmented")}/>
      {/if}
      <img class="h-15 hover:scale-105" src="./user.png" onclick={() => there_is_no_way_to_extract_out_a_pop_up = true}/>
    </div>
    <div class="absolute bottom-0 metallic h-8 w-full down-shadow"></div>
  </div>
</div>

{#if there_is_no_way_to_extract_out_a_pop_up}
  <div class="fixed inset-0 flex items-center justify-center bg-black/40 backdrop-blur-[2px] z-9999">
    <div class="bg-white">
      <h1 class="text-red-600 text-7xl bg-white">JUST A TESTING MENU</h1>
      <button class="bg-red-600 rounded-full text-white"
        onclick={
          () => {
            company = company ? null : 2  // Become Chill Walmart
            there_is_no_way_to_extract_out_a_pop_up = false
          }
        }
      >
        TOGGLE BETWEEN USER AND COMPANY PROFILE
      </button>
    </div>
  </div>
{/if}

{#if !company}
  <Freebies />
{:else}
  <div class="relative flex justify-center h-full">
    <div class="w-90 mx-5">
      <div class="fixed top-25 flex flex-col items-center gap-5 w-90">
        <div class="flex items-end justify-between w-full">
          <h2 class="text-4xl font-light">Savings:</h2>
          <p class="text-4xl">$14,496.32</p>
        </div>
        <div class="flex items-end justify-between w-full">
          <h2 class="text-4xl font-light">People Helped:</h2>
          <p class="text-4xl">2,071</p>
        </div>
        <div class="metallic m-5 h-30 w-58 rounded-full flex justify-center items-center shadow-md/50 hover:scale-105 duration-105"
          onclick={() => alert("Not implmented")}
        >
          <div class="bg-white h-22 w-50 inset-shadow-sm/50 rounded-full flex justify-center items-center text-center">
            <p>Export Itemized Tax Deductions</p>
          </div>
        </div>
      </div>
    </div>
    <div class="grid grid-cols-3 gap-5 w-fit mb-20">
      {#each site_data.freebies.filter((x) => x.company == company) as freebie}
        <div class="relative">
          <Freebie class="h-95 w-75" hide_footer={true} data={freebie}/>

          <div class="absolute bottom-4 -right-2 p-2 backdrop-blur-sm shadow-md/30 rounded-2xl flex justify-center hover:scale-105 duration-150"
            onclick={() => alert("not implmented")}
          >
            <img class="h-8 drop-shadow-md/60" src="./edit.png"/>
          </div>
        </div>
      {/each}
      <div class="fixed bottom-4 right-4 metallic h-30 w-30 rounded-full flex justify-center items-center shadow-md/50 hover:scale-105 duration-105"
        onclick={() => alert("not implmented")}
      >
        <div class="bg-white h-22 w-22 inset-shadow-sm/50 rounded-full flex justify-center items-center text-center">
          <p>Create Donation</p>
        </div>
      </div>
    </div>
  </div>
{/if}

<style>

.down-shadow {
  box-shadow: 0px 5px 6px -1px rgb(0 0 0 / 0.5);
}

</style>
