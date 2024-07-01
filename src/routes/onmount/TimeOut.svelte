<script>
    import { onMount } from "svelte";
    let count = 0;
    let intervalId;
    onMount(() => {
      intervalId = setInterval(() => {
        count++;
              console.log(count)
      }, 1000);
  
      return () => {
        clearInterval(intervalId);
      };
    });
  </script>
  
  {count}
  