<script>
  import { fade, scale } from "svelte/transition";
  import FeedbackItem from "./FeedbackItem.svelte";

  import { feedbackList } from "../store";
</script>

{#each $feedbackList as feedback (feedback.id)}
  <div in:scale out:fade={{ duration: 500 }}>
    <FeedbackItem item={feedback} />
  </div>
{/each}
