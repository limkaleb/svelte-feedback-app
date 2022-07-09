<script>
  import FeedbackList from '../components/FeedbackList.svelte'
	import FeedbackStats from '../components/FeedbackStats.svelte'
	import FeedbackForm from '../components/FeedbackForm.svelte'

	let feedback = [
		{
			id: 1,
			rating: 10,
			text: 'Lorem ipsum dolor sit amet. Et autem cumque est labore culpa et libero ipsa aut tempore voluptatum et consequatur consequatur. Et dolorum exercitationem ut culpa accusamus qui ipsa repellendus qui quae consequatur sed voluptatem neque sit harum officiis.',
		},
		{
			id: 2,
			rating: 9,
			text: 'Lorem ipsum dolor sit amet. Et autem cumque est labore culpa et libero ipsa aut tempore voluptatum et consequatur consequatur. Et dolorum exercitationem ut culpa accusamus qui ipsa repellendus qui quae consequatur sed voluptatem neque sit harum officiis.',
		},
		{
			id: 3,
			rating: 8,
			text: 'Lorem ipsum dolor sit amet. Et autem cumque est labore culpa et libero ipsa aut tempore voluptatum et consequatur consequatur. Et dolorum exercitationem ut culpa accusamus qui ipsa repellendus qui quae consequatur sed voluptatem neque sit harum officiis.',
		},
	]

	$: count = feedback.length
	$: average = feedback.reduce((a, { rating }) => a + rating, 0) / feedback.length

	const deleteFeedback = (/** @type {{ detail: any; }} */ e) => {
		console.log('eeE: ', e)
		const itemId = e.detail
		feedback = feedback.filter((item) => item.id != itemId)
	}
</script>

<FeedbackForm />
<FeedbackStats {count} {average} />
<FeedbackList {feedback} on:delete-feedback={deleteFeedback} />

