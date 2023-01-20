<script lang="ts">
	type Design = 'modern' | 'classic';
	type Item = Record<string, any>;

	interface Column {
		target: string;
		title: string;
		build?(item: any): any;
	}

	export let design: Design = 'modern';
	export let columns: Column[] = [];
	export let items: Item[] = [];

	const classList = ['table', design ? `design-${design}` : ''].join(' ');
</script>

<table class={classList}>
	<thead>
		<tr>
			{#each columns as { target, title }}
				<th id={target}>{title}</th>
			{/each}
		</tr>
	</thead>
	<tbody>
		{#each items as item}
			<tr>
				{#each Object.entries(item) as [_key, val]}
					<td>{val}</td>
				{/each}
			</tr>
		{/each}
	</tbody>
</table>

<style>
	* {
		box-sizing: border-box;
	}

	.table {
		table-layout: fixed;
		border-collapse: collapse;
		margin: 25px 0;
		font-size: 0.9em;
		font-family: sans-serif;
		min-width: 400px;
		box-shadow: 0 0 20px rgba(0, 0, 0, 0.15);
	}

	.table thead tr {
		background-color: #009879;
		color: #ffffff;
		text-align: left;
	}

	.table th,
	.table td {
		padding: 12px 15px;
	}

	.table tbody tr {
		border-bottom: 1px solid #dddddd;
		transition: transform 0.3s ease-in;
	}

	.table tbody tr:nth-of-type(even) {
		background-color: #f3f3f3;
	}

	.table tbody tr:last-of-type {
		border-bottom: 2px solid #009879;
	}

	.table tbody tr:hover {
		/* font-weight: bold; */
		color: #009879;
		transform: scale(1.03);
	}

	/* Design */
	/* .design-modern {

	}

	.design-classic {
		
	}*/
</style>
