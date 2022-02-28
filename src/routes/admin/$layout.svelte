<script>
	import Sidebar from '$lib/Sidebar/sidebar.svelte';
	import SidebarMini from '$lib/Sidebar/sidebar-mini.svelte';
	import HeaderAdmin from '$lib/Header/admin.svelte';
	import { Divider } from 'svelte-materialify';
</script>

<main class="admin">
	<div class="md:flex md:flex-cols-2">
		<div class="flex flex-cols-2">
			<div class="mini-side">
				<SidebarMini />
			</div>
			<div class="sidebar">
				<Sidebar/>
			</div>
		</div>
		<div class="main-content">
			<div class="header">
				<HeaderAdmin/>
				<span>Dasboard</span>
			</div>
			<div class="content">
				<slot/>
			</div>
		</div>
	</div>
</main>

<style lang="scss">
	.main-content{
		width: 86%;
		.header{
			border-bottom: 1px solid #083a45;
			padding-bottom: 10px;
			span{
				font-style: normal;
				font-weight: 700;
				padding: 15px;
    		font-size: 35px;
			}
		}
	}
</style>