<script>
  let box = {
    locked: true,
    contents: [
      "Thing 1",
      "Thing 2",
      "Thing 3"
    ]
  }

  function lock() {
    box.locked = true
  }

  function unlock() {
    box.locked = false
  }
</script>

<h1>The Box</h1>

{#if box.locked}
  <p>The box is locked.</p>
  <button on:click={unlock}>Unlock</button>
  <!-- do nothing when box is locked. -->

{:else}
  <p>The box is unlocked.</p>
  <button on:click={lock}>Lock</button>
  <ul>
    {#each box.contents as item}
      <li>{item}</li>
    {/each}
  </ul>
  
{/if}
