<script lang="ts">

    import "./homelist.scss"
    import HomelistItem from "./HomelistItem.svelte";

    let amountOfItems = 12;
    let amountOfIndex:number[] = [];
    let activeIndex = 0;



	// if amountOfItems not divisible by 5, add one more index
	if (amountOfItems % 5 != 0) {
		// divide the amount of items by 5 and round up to the top
		amountOfIndex = Array.from(Array(Math.ceil(amountOfItems / 6)).keys());
	}
	if (amountOfItems % 5 == 0) {
		// divide the amount of items by 5 and round up to the top
		amountOfIndex = Array.from(Array(Math.ceil(amountOfItems / 6)).keys());
	}


</script>

<div class="flex justify-between items-end listHeader">
  <h1 class="text-2xl">Popular Games on Boardio</h1>
  <div class="flex gap-2">
    {#each amountOfIndex as index}
      <div class="w-4 h-1 bg-gray-600 {activeIndex === index ? 'bg-stone-400' : ''}"></div>
    {/each}
  </div>
</div>

<div class="flex justify-between items-center itemList" style="--index: {activeIndex}">
  {#if activeIndex != 0}
    <button class="left-button text-black" on:click={() => activeIndex--}>
		<svg xmlns="http://www.w3.org/2000/svg" class="h-16 w-16 text-stone-300" fill="none" viewBox="0 0 24 24" stroke="currentColor">
			<path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M15 19l-7-7 7-7" />
		</svg>
	</button>
  {/if}
  <div class="item-container">
    <HomelistItem />
	<HomelistItem />
	<HomelistItem />
	<HomelistItem />
	<HomelistItem />
	<HomelistItem />
	<HomelistItem />
	<HomelistItem />
	<HomelistItem />
	<HomelistItem />
	<HomelistItem />
	<HomelistItem />
  </div>
  {#if activeIndex != amountOfIndex.length - 1}
    <button class="right-button text-black flex items-center justify-center" on:click={() => activeIndex++}>
		<svg xmlns="http://www.w3.org/2000/svg" class="h-16 w-16 text-stone-300" fill="none" viewBox="0 0 24 24" stroke="currentColor">
			<path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M9 5l7 7-7 7" />
		</svg>
	</button>
  {/if}
</div>
