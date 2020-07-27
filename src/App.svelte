<script>
  import { onMount } from "svelte";
  export let date;

  onMount(async () => {
    const res = await fetch("/api/date");
    const newDate = await res.text();
    date = newDate;
  });
</script>

<main>
  <img src="rebus.png" alt="rebus">
  <p>{date ? date : 'Loading date...'}</p>
</main>
