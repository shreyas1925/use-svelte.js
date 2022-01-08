<script>
  import FeedbackForm from "./Components/FeedbackForm.svelte";
  import FeedbackList from "./Components/FeedbackList.svelte";
  import FeedbackStats from "./Components/FeedbackStats.svelte";

  let feedback = [
    {
      id: 1,
      rating: 9,
      text: "lorem ipsum dolor sit amet, consectetur",
    },
    {
      id: 2,
      rating: 8,
      text: "lorem ipsum dolor sit amet, consectetur",
    },
    {
      id: 3,
      rating: 8,
      text: "lorem ipsum dolor sit amet, consectetur",
    },
  ];

  $: count = feedback.length;
  $: average = Math.round(
    feedback.reduce((a, { rating }) => a + rating, 0.0) / feedback.length
  );

  const addFeedback = (e) => {
    const newfeedback = e.detail;
    feedback = [newfeedback, ...feedback];
  };

  // float_num.toFixed(2);
  const delFeedback = (e) => {
    const itemId = e.detail;
    feedback = feedback.filter((item) => item.id != itemId);
  };
</script>

<main class="container">
  <FeedbackForm on:add-feedback={addFeedback} />
  <FeedbackStats {count} {average} />
  <FeedbackList {feedback} on:del-feedback={delFeedback} />
</main>
