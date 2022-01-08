<script>
  import { fade, scale } from "svelte-transition";
  import FeedbackItem from "./FeedbackItem.svelte";
  export let feedback = [];
  console.log(feedback);
</script>

<main>
  {#each feedback as fb (fb.id)}
    <div in:scale out:fade={{ duration: 500 }}>
      <FeedbackItem item={fb} on:del-feedback />
    </div>
  {/each}
</main>
