<script>
    let name = "world";
    let checked = false;
    import TimeOut from "./TimeOut.svelte";
      import Fetch from './Fetch.svelte'
  </script>
  
  <input type="checkbox" bind:checked />
  
  {#if checked}
    <TimeOut />
      <Fetch />
  {/if}