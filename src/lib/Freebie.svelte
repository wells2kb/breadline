<script>
  import TravelTimes from '$lib/TravelTimes.svelte'
  import { site_data } from '$lib/SiteData.js'
  const props = $props();
</script>

<button class={"relative flex flex-col items-center " + props.class + (props.onclick ? " hover-image" : "")} onclick={props.onclick ?? (() => {})}>
  <img class="rounded-lg object-cover h-full w-full" src="{props.data.image}"/>
  <h2 class="absolute w-full top-5 font-bold backdrop-blur-xl text-center text-white tracking-[0.05em] text-shadow-lg/30">{props.data.name}</h2>
  <div class="absolute top-1 right-1 metallic shadow-xl/50 rounded-full">
    <h3 class="px-2 text-center font-medium text-xl items-center">{props.data.quantity}</h3>
  </div>
  {#if !props.hide_footer}
    <h2 class="absolute backdrop-blur-xl bottom-8.5 h-8 w-full px-2 font-semibold text-center text-white text-shadow-lg">{site_data.companies[props.data.company].name}</h2>
    <TravelTimes class="absolute bottom-2 w-[90%] px-2"/>
  {/if}
</button>

<style>
.hover-image > img {
  transition: all 150ms ease-in-out;
}
.hover-image:hover > img {
  transform: scale(1.05);
}
.hover-image > h2 {
  transition: all 150ms ease-in-out;
}
.hover-image:hover > h2 {
  width: 105%;
}

</style>
