<script>
	import { page } from '$app/stores';
	import AutoDashboard from '$lib/components/AutoDashboard.svelte';
	import Chart from '$lib/components/Chart.svelte';
	import Dashboard from '$lib/components/Dashboard.svelte';
	import { nowSec } from '$lib/time';

	let id = $page.params.id;
</script>

<main class="p-4">
	<a class="text-4xl link link-hover" href="/">Microeye</a>

	<div class="breadcrumbs">
		<ul>
			<li>
				<a href="/dashboards" class="link link-hover">Dashboards</a>
			</li>
			<li>{$page.params.id}</li>
		</ul>
	</div>

	<AutoDashboard dashId={id} fromSec={nowSec(-60)} toSec={nowSec()} refreshIntervalSec={1} />
</main>
