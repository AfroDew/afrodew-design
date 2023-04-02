<script lang="ts">
	import { Button, Input, Text, Chips, Table, AppBar, Card } from '$lib/components';
	import Dialog from '$lib/components/Dialog.svelte';

	let openDialog = false;

	const toggleDialog = () => (openDialog = !openDialog);
</script>

<AppBar />
<Text tag="h1">Heading 1</Text>
<Text tag="p">Paragraph</Text>
<Button>Button</Button>
<Button tag="a" href="#">Button Link</Button>
<Button outline="plain">Button Outline: Plain</Button>
<Input label="Label" placeholder="Enter here" />

<!-- Card -->
<section>
	<Card
		elevated
		class="sss"
		on:click={(e) => {
			console.log(e);
		}}>Card</Card
	>
</section>

<!-- Dialog -->
<div>
	<Button on:click={toggleDialog}>Toggle Dialog</Button>
	<Dialog
		open={openDialog}
		closed={() => {
			openDialog = false;
		}}
	>
		<div slot="head">
			<Text tag="h2">Dialog Head</Text>
		</div>
		<div>
			<Text tag="h3">Dialog Content</Text>
		</div>
		<div slot="footer">
			<Button>Button</Button>
		</div>
	</Dialog>
</div>

<!-- Chips -->
<div>
	<Text tag="h2">Chips</Text>
	<Chips
		items={['snake', 'Jumping Cat', 'Storm', 'Sting']}
		added={(item, items) => {
			console.log(`[chip:added] ${item} -> ${items}`);
		}}
		removed={(item, items) => {
			console.log(`[chip:removed] ${item} -> ${items}`);
		}}
	/>
</div>

<!-- Table -->
<div>
	<Text tag="h2">Table</Text>
	<Table
		columns={[
			{ target: 'name', title: 'Name' },
			{ target: 'age', title: 'Age' },
			{ target: 'email', title: 'Email' }
		]}
		items={[
			{ name: 'Storm', age: 20, email: 'storm@xxx.xxx' },
			{ name: 'Storm', age: 23, email: 'storm@xxx.xxx' },
			{ name: 'Storm', age: 20, email: 'storm@xxx.xxx' },
			{ name: 'Storm', age: 20, email: 'storm@xxx.xxx' }
		]}
	/>
</div>

<style>
	section {
		padding: 2rem;
	}
</style>
