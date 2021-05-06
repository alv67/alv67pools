<script>
	import Header from './components/Header.svelte';
	import Footer from './components/Footer.svelte';
	import PollList from './components/PollList.svelte';
	import CreatePoolForm from './components/CreatePoolForm.svelte';
	import Tabs from './shared/Tabs.svelte';

	// tabs
	export let name;
	let items = ['Current Polls', 'Add New Poll'];
	let activeItem = 'Current Polls';
	const tabChange = (e) => {
		activeItem = e.detail;
	}

	// pools
	let polls = [
		{
			id: 1,
			question: 'Python or Javascript ?',
			answerA: 'Python',
			answerB: 'Javascript',
			votesA: 9,
			votesB: 15,
		},
	];

	const handleAdd = (e) => {
		const poll = e.detail;
		polls = [poll, ...polls];
		activeItem = 'Current Polls';
	}

	const handleVote = (e) => {
		const { id, option } = e.detail;
		let copiedPolls = [...polls];
		let upvotedPoll = copiedPolls.find((poll) => poll.id == id);
		if (option === 'a') {
			upvotedPoll.votesA++;
		}
		if (option === 'b') {
			upvotedPoll.votesB++;
		}
		polls = copiedPolls;
	}
</script>

<Header />
<main>
	<Tabs {activeItem} items={items} on:tabChange={tabChange}/>
	{#if activeItem === 'Current Polls'}
		<PollList {polls} on:vote = {handleVote}/>
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