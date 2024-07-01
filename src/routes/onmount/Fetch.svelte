<script>
    import { onMount } from "svelte";
    let src;
    let intervalId;
    onMount(() => {
        const controller = new AbortController();
          const signal = controller.signal;
  
          fetch("https://dog.ceo/api/breeds/image/random", { signal })
              .then((response) => response.json())
              .then(({message}) => {src = message})
  
          return () => {
              controller.abort();
          }
          });
  </script>
  
  <img src={src} alt="text"/>
  
  