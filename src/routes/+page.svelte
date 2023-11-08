<script lang="ts">

	//import components
	import HeroSection from '$lib/Components/HeroSection/HeroSection.svelte';
	import Homelist from '$lib/Components/Lists/HomeList/Homelist.svelte';

</script>

<svelte:head>
	<title>Home</title>
</svelte:head>

<HeroSection />
<div class="-mt-20 relative z-50 mb-10">
	<Homelist />
</div>
