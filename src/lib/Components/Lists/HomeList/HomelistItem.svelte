<script lang="ts">
	import "./homelist.scss"
</script>

<div class="item-wrapper">
	<div class="item-image"></div>
	<div class="item-content flex justify-between w-full items-center">
		<div>
		<h1>title</h1>
			<div class="genres flex">
				<span>genre</span>
			</div>
		</div>
		<div class="item-rating">
			<!-- icon for adding to list -->
			<svg xmlns="http://www.w3.org/2000/svg" class="h-8 w-8 text-stone-300" fill="none" viewBox="0 0 24 24" stroke="currentColor">
				<path stroke-linecap="round" stroke-linejoin="round" stroke-width="2"
					d="M12 6v6m0 0v6m0-6h6m-6 0H6" />
			</svg>
		</div>
	</div>
</div>
