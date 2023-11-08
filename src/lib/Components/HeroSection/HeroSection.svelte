<script lang="ts">
    import Play_arrow from 'svelte-google-materialdesign-icons/Play_arrow.svelte';
    import Info from 'svelte-google-materialdesign-icons/Info.svelte';
</script>

<style>
    .heroSection {
        width: 100%;
        aspect-ratio: 21/9;
        position: relative;
    }
    .hero-background {
        background-image: url('heroSection/cyberpunk.jpeg');
        background-size: cover;
        background-position: center;
        filter: brightness(0.5);
        position: absolute;
        top: 0;
        left: 0;
        width: 100%;
        height: 100%;
    }
    .heroContent {
        position: absolute;
        top: 0;
        left: 0;
        width: 100%;
        height: 100%;
        display: flex;
		flex-direction: row-reverse;
        justify-content: space-between;
		align-items: center;
        padding: 0 0 0 5%;
        gap: 20px;
		background-image: linear-gradient(to bottom, rgba(0, 0, 0, 0) 80%, #121212 100%);
    }
    .hoverInfo:hover{
        background-color: rgb(87 83 78 / 60%);
    }
</style>

<div class="heroSection">
    <div class="hero-background"></div>
    <div class="heroContent">
		<div class="h-4/6">
			<div class="flex flex-col h-full justify-end">
					<h1 class="px-5 bg-stone-500 text-xl">18+</h1>
			</div>
		</div>
        <div class="flex w-1/4 flex-col gap-4">
            <img src="heroSection/cyberpunk_logo.png" alt="">
            <p class="text-xl text-justify">Explore this futuristic RPG togheter with the legendary character Johny Silverhand. Take on Arasaka in an epic battle where your life is on the line.</p>
            <div class="flex gap-2">
                <button class="hover:bg-gray-300 flex py-2 px-6 gap-1 justify-end bg-white rounded-lg items-center">
                    <Play_arrow size="35" color="Black"/>
                    <h2 class="text-2xl text-black">Play</h2>
                </button>
                <button class="flex py-2 px-6 gap-1 justify-end bg-stone-600 opacity-80 hoverInfo rounded-lg items-center">
                    <Info size="35"/>
                    <h2 class="text-2xl">More Info</h2>
                </button>
            </div>
        </div>
    </div>
</div>
