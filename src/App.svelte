<script>
	import FeedbackList from "./components/FeedbackList.svelte";

	let feedback = [
		{
			id: 1,
			rating: 10,
			text:  'some text for testing pourposes only please dont read me '
		},
		{
			id: 2,
			rating: 6,
			text:  'some text for testing pourposes only please dont read me '
		},
		{
			id: 3,
			rating: 9,
			text:  'some text for testing pourposes only please dont read me '
		},
		{
			id: 4,
			rating: 2,
			text:  'some text for testing pourposes only please dont read me '
		},
	]

	$: count = feedback.length
	$: average = feedback.reduce((a, {rating}) =>a + rating, 0) / feedback.length
	const deleteFeedback = (e) =>{
		const itemId = e.detail
		feedback = feedback.filter((item) => item.id != itemId )
	}
</script>

<main class="container">
	<h1>{average}</h1>
<FeedbackList {feedback}  on:delete-feedback={deleteFeedback}/>

</main>
