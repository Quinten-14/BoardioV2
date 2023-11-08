<script lang="ts">
    import Notifications from 'svelte-google-materialdesign-icons/Notifications.svelte';
    import Search from 'svelte-google-materialdesign-icons/Search.svelte';
	import Account_circle from 'svelte-google-materialdesign-icons/Account_circle.svelte';
	import Expand_more from 'svelte-google-materialdesign-icons/Expand_more.svelte';

    let amountNotifications = 1;
    let showSearchBox = false;
    let loggedIn = true;

    function toggleSearchBox() {
        showSearchBox = !showSearchBox;
    }
</script>

<style>
    .nav_links li a {
        transition: all 0.2s ease-in-out;
    }
    .notification-count {
        position: relative;
        user-select: none;
    }
    .notification-count > h1 {
        position: absolute;
        top: -5px;
        right: -5px;
        width: 20px;
        height: 20px;
        display: flex;
        align-items: center;
        justify-content: center;
        border-radius: 50%;
        background-color: red;
        color: white;
        font-size: 12px;
    }
    .search-box {
        width: 200px;
        height: 30px;
        border: 1px solid #ccc;
        border-radius: 5px;
        padding: 5px;
        background-color: transparent;
    }
	.profile .expand{
		transition: all 0.2s ease-in-out;
	}
	.profile:hover > .expand{
			transform: rotate(180deg);
			transition: all 0.2s ease-in-out;
	}
</style>

<nav class="flex justify-between px-16 py-6 fixed w-full top-0 z-50">
    <div class="flex items-center gap-16">
        <div>
            <a href="/">
                <img src="images/logo.svg" alt="" />
            </a>
        </div>
        <div>
            <ul class="flex gap-6 nav_links">
                <li><a class="hover:text-stone-400" href="/">Home</a></li>
                <li><a class="hover:text-stone-400" href="/">Boardgames</a></li>
                <li><a class="hover:text-stone-400" href="/">Video Games</a></li>
                <li><a class="hover:text-stone-400" href="/">New & Popular</a></li>
                <li><a class="hover:text-stone-400" href="/">My List</a></li>
            </ul>
        </div>
    </div>
    <div class="flex items-center gap-4">
        <div class="searchBox">
        {#if !showSearchBox}
            <Search size="30" on:click={toggleSearchBox}/>
        {:else}
            <div class="flex gap-1">
            <Search size="30" on:click={toggleSearchBox}/>
            <input class="search-box" type="text" placeholder="Titles, Creators, genres"/>
            </div>
        {/if}
        </div>
        {#if loggedIn}
        <div class="flex items-center">
            <div class="notification-count">
                <Notifications size="30"/>
                {#if amountNotifications > 0}
                    <h1>{amountNotifications}</h1>
                {/if}
            </div>
        </div>
		<div class="flex items-center profile">
			<Account_circle size="30"/>
			<div class="expand">
			<Expand_more size="25"/>
			</div>
		</div>
        {:else}
        <div class="flex items-center gap-4">
            <button class="bg-stone-600 hover:bg-stone-500 text-white font-bold py-2 px-4 rounded">
                Sign in
            </button>
            <button class="bg-stone-600 hover:bg-stone-500 text-white font-bold py-2 px-4 rounded">
                Sign up
            </button>
        </div>
        {/if}
    </div>
</nav>
