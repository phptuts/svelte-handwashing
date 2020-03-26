<script>
  export let progress = 20;
</script>

<style>
  .sr-only {
    display: none;
  }
  .progress-bar {
    height: 30px;
    background-color: rgb(77, 199, 55);
  }
  .progress-container {
    margin: 20px 0;
    border: solid rgb(194, 194, 194) 1px;
  }
</style>

<div bp="grid">
  <div class="progress-container" bp="offset-5@md 4@md 12@sm">
    <div class="progress-bar" role="progressbar" style="width: {progress}%">
      <span class="sr-only">{progress}% Complete</span>
    </div>
  </div>

</div>
