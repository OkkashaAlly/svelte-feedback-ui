<script>
  import FeedbackList from "./components/FeedbackList.svelte";

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

  const deleteFeedback = e => {
    const itemId = e.detail;

    feedbackList = feedbackList.filter(feedback => feedback.id !== itemId);
  };
</script>

<main class="container">
  <FeedbackList {feedbackList} on:delete-feedback={deleteFeedback} />
</main>

<style>
</style>
