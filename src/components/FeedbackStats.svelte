<script>
  import { feedbackList } from "../store";
  $: count = $feedbackList.length;
  $: average = $feedbackList.reduce((a, { rating }) => a + rating, 0) / count;
</script>

<div class="feedback-stats">
  <h4>{count} Reviews</h4>
  <h4>Ratings Average: {isNaN(average) ? 0 : average}</h4>
</div>

<style>
  .feedback-stats {
    display: flex;
    justify-content: space-between;
    align-items: center;
  }
</style>
