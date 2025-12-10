<script>
  const props = $props();
</script>

<div class={"metallic shadow-lg/30 rounded-full px-2 " + props.class}>
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
