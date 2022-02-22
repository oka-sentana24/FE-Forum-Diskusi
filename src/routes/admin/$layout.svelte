<script>
	import Sidebar from '$lib/Sidebar/sidebar.svelte';
	import SidebarMini from '$lib/Sidebar/sidebar-mini.svelte';
	import HeaderAdmin from '$lib/Header/admin.svelte';
</script>

<main class="admin">
	<div class="md:flex md:flex-cols-2 md:gap-5">
		<div class="flex flex-cols-2">
			<div class="mini-side">
				<SidebarMini />
			</div>
			<div class="sidebar">
				<Sidebar/>
			</div>
		</div>
		<div>dddddd</div>
	</div>
</main>

<!-- <div class="main-admin">
	<div class="admin-content">
		<div class="mini-side">
				<SidebarMini />
		</div>
		<div class="sidebar">
			<Sidebar />
		</div>
		<div class="content">
			<div>
				<HeaderAdmin/>
				<div class="title">
					Dasboard
				</div>
			</div>
			<div class="py-5">
				<slot/>
			</div>
		</div>
	</div> -->
	
	<!-- <div>
		<Sidebar />
	</div> -->
	<!-- <div class="admin-content">
		<div class="mini-sidebar">
			<SidebarMini />
		</div>
		<div class="content-nav">
			<Sidebar />
		</div>
		<div class="content-page w-full px-5">
			<HeaderAdmin/>
			<slot />
		</div>
	</div> -->
<!-- </div> -->
