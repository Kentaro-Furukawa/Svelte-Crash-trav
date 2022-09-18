<script>
	import FeedbackForm from "./componets/FeedbackForm.svelte"
	import FeedbackList from "./componets/FeedbackList.svelte"
	import FeedbackStats from "./componets/FeedbackStats.svelte"
	import {FeedbackStore} from './stores';

</script>

<main class="container">
	<FeedbackForm />
	<FeedbackStats />
	<FeedbackList/>
</main>
