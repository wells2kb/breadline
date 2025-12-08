<script>
  import Freebies from "$lib/Freebies.svelte"
</script>

<div class="h-18 mb-5">
  <div class="fixed w-full h-18 z-1 bg-gray-400/10 backdrop-blur-xl">
    <img class="absolute top-0 left-8 h-15 z-1 drop-shadow-xl/50" src="./logo.png"/>
    <div class="absolute bottom-0 metallic h-8 w-full down-shadow"></div>
  </div>
</div>

<div class="grid grid-cols-3 gap-5 w-fit mx-auto">
  <Freebies />
</div>

<style>

.down-shadow {
  box-shadow: 0px 5px 6px -1px rgb(0 0 0 / 0.5);
}

</style>
