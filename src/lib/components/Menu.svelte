<script>
	import { createEventDispatcher } from "svelte";


    const dispatch = createEventDispatcher();


    function closeMenu() {
        dispatch('closeMenu')
    }
    
</script>

<div class="p-5 bg-gray-900 h-screen text-white">
    <button on:click={closeMenu}><img class="w-6 h-6" src="https://www.svgrepo.com/show/124304/three-dots.svg"/></button>
    <ul class="flex flex-col gap-y-5"> 
        <li>Items</li>
        <li>Warehouse</li>
        <li>Orders</li>
        <li>Clients</li>
    </ul>
</div>