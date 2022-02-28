<script>
	export let breadcrumbs = [];
</script>
<div>
	{#each breadcrumbs as bc}
		<a href="/#/{bc.path}">{bc.name}</a>
	{/each}
</div>

<style>
	div{font-size:12px;}
	div a{ color:grey;}
	div a:not(:last-child):after{content:'/'; margin: 0 10px}
</style>