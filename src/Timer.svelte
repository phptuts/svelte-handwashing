<script>
  import { createEventDispatcher } from "svelte";
  import ProgressBar from "./ProgressBar.svelte";
  const dispatch = createEventDispatcher();
  let secondsLeft = 20;
  $: progress = ((20 - secondsLeft) / 20) * 100;
  let isRunning = false;
  let timer;
  function startTimer() {
    isRunning = true;
    timer = setInterval(() => {
      secondsLeft -= 1;
      if (secondsLeft <= 0) {
        clearInterval(timer);
        secondsLeft = 20;
        isRunning = false;
        dispatch("play", true);
      }
    }, 1000);
  }
</script>

<style>
  .start {
    background-color: rgb(154, 73, 73);
  }
  button[disabled] {
    background-color: #f3f3f3;
    cursor: not-allowed;
  }
  h2 {
    margin: 0;
  }
</style>

<div bp="grid">

  <h2 bp="offset-5@md 4@md 12@sm">Seconds Left: {secondsLeft}</h2>
</div>

<ProgressBar {progress} />
<div bp="grid">

  <button
    bp="offset-5@md 4@md 12@sm"
    disabled={isRunning}
    on:click={startTimer}
    class="start">
    Start
  </button>
</div>
