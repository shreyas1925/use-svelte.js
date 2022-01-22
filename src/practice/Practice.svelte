<script>
  let name = "Shreyas";
  let age = 19;
  let para = false;
  let color = "#db5f36";
  
  $: bio = `Heyy I am ${name} , ${age} years old! `;
  
  let students = [
    {
      id: 1,
      name: "John",
    },
    { id: 2, name: "Mary" },
    { id: 3, name: "Brian" },
  ];
  
  const toggle = () => {
    para = !para;
    students = [...students, { id: 4, name: "July" }];
    color = color === "#db5f36" ? "green" : "#db5f36";
  };
</script>

<main>
  <h1 style="color:{color}">{bio}!</h1>
  {#if para}
    <p>
      Visit the <a href="https://svelte.dev/tutorial">Svelte tutorial</a> to learn
      how to build Svelte apps.
    </p>
  {:else}
    <p>Sorry no datas to display</p>
  {/if}
  <button on:click={toggle} style="cursor:pointer">Toggle✌️</button>
  {#each students as student (student.id)}
    <p>{student.id}. {student.name}</p>
  {/each}
</main>

<style>
  main {
    text-align: center;
    padding: 1em;
    max-width: 240px;
    margin: 0 auto;
  }
  p {
    font-weight: 800;
    font-size: 20px;
  }
  h1 {
    color: #db5f36;
    text-transform: uppercase;
    font-size: 4em;
    font-weight: 600;
  }

  @media (min-width: 640px) {
    main {
      max-width: none;
    }
  }
</style>
