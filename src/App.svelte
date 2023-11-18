<script>
  import FeedbackForm from "./components/FeedbackForm.svelte";
  import FeedbackList from "./components/FeedbackList.svelte";
  import FeedbackStats from "./components/FeedbackStats.svelte";

  let feedbackList = [
    {
      id: 1,
      rating: 10,
      text: "Lorem ipsum dolor sit amet consectetur adipisicing elit. consequuntur vel vitae commodi alias voluptatem est voluptatum ipsa quae.",
    },
    {
      id: 2,
      rating: 9,
      text: "Lorem ipsum dolor sit amet consectetur adipisicing elit. consequuntur vel vitae commodi alias voluptatem est voluptatum ipsa quae.",
    },
    {
      id: 3,
      rating: 8,
      text: "Lorem ipsum dolor sit amet consectetur adipisicing elit. consequuntur vel vitae commodi alias voluptatem est voluptatum ipsa quae.",
    },
  ];

  $: count = feedbackList.length;
  $: average = feedbackList.reduce((a, { rating }) => a + rating, 0) / count;

  const deleteFeedback = e => {
    const itemId = e.detail;

    feedbackList = feedbackList.filter(feedback => feedback.id !== itemId);
  };

  const addNewFeedback = e => {
    const newFeedback = e.detail;

    feedbackList = [newFeedback, ...feedbackList];
  };
</script>

<main class="container">
  <FeedbackForm on:add-new-feedback={addNewFeedback} />
  <FeedbackStats {count} {average} />
  <FeedbackList {feedbackList} on:delete-feedback={deleteFeedback} />
</main>

<style>
</style>
