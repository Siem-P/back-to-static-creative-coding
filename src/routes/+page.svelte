<script>
    import { onMount } from "svelte";
	import Loader from "$lib/components/Loader.svelte";
    
    onMount(() => {
    document.body.classList.add('single-grid')
})
</script>


<Loader />

