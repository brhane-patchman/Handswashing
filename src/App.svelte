<script>
import Timer from "./Timer.svelte";
import Howto from "./Howto.svelte";
let audio;
function timerStarts(e) {
    audio.play();
}
function stopAudio(e) {
    audio.pause();
    audio.currentTime = 0;
}
</script>

<style>
h1, h3 {
    text-align: center;
}
a {
    padding-right: 10px;
}
</style>
<h1>
	Washing Hand App
</h1>

<Timer on:start={timerStarts} on:end={stopAudio}/>

<Howto/>

<h3>
<a href="https://www.who.int/gpsc/clean_hands_protection/en/">Picture source </a>
<a href="https://freesound.org/people/metrostock99/sounds/345086/"> Sound source</a>
</h3>

<audio bind:this={audio}>
    <source src="sound.wav">
    <track kind="captions" srclang="en" label="english_captions">
</audio>