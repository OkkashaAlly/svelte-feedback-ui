<script>
  import FeedbackItem from "./FeedbackItem.svelte";

  export let feedbackList = [];
</script>

{#each feedbackList as feedback}
  <FeedbackItem item={feedback} />
{/each}
