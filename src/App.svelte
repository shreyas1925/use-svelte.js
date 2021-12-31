<script>
  import FeedbackList from "./Components/FeedbackList.svelte";

  const feedback = [
    {
      id: 1,
      rating: 8,
      text: "lorem ipsum dolor sit amet, consectetur",
    },
  ];
</script>

<main>
  <FeedbackList {feedback} />
</main>
