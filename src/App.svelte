<script>
  import HowTo from "./HowTO.svelte";
  import Timer from "./Timer.svelte";
  let sound;
  function play() {
    sound.play();
  }
</script>

<style>
  h1 {
    text-align: center;
  }
</style>

<div bp="grid">
  <h1 bp="12">Hand Washing App</h1>
</div>
<Timer on:play={play} />
<HowTo />
<div bp="grid">
  <h3 bp="offset-5@md 4@md 12@sm">
    <a href="https://www.who.int/gpsc/clean_hands_protection/en/">
      Picture Source
    </a>
    <a href="https://freesound.org/people/metrostock99/sounds/345086/">
      Sound Attribution
    </a>
  </h3>
</div>
<audio bind:this={sound}>
  <source src="sound.wav" type="audio/wav" />
</audio>
