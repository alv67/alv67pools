<script>
	import Header from './components/Header.svelte';
	import Footer from './components/Footer.svelte';
	import PollList from './components/PollList.svelte';
	import CreatePoolForm from './components/CreatePoolForm.svelte';
	import Tabs from './shared/Tabs.svelte';

	// tabs
	let items = ['Current Polls', 'Add New Poll'];
	let activeItem = 'Current Polls';
	const tabChange = (e) => {
		activeItem = e.detail;
	}

	const handleAdd = (e) => {
		// const poll = e.detail;
		// polls = [poll, ...polls];
		activeItem = 'Current Polls';
	}

</script>

<Header />
<main>
	<Tabs {activeItem} items={items} on:tabChange={tabChange}/>
	{#if activeItem === 'Current Polls'}
		<PollList />
	{:else if activeItem === 'Add New Poll'}
		<CreatePoolForm on:add={handleAdd} />
	{/if}
</main>
<Footer />

<style>
	main{
		max-width: 960px;
		margin: 40px auto;
	}
</style>