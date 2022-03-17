<script>
	import Timer from "./Timer.svelte";
	import HowTo from "./HowTo.svelte";
	let audio;

	function timerEnds(e) {
		audio.play();
	}
</script>

<h1>Handwashing App</h1>

<Timer on:end={timerEnds} />
<HowTo />

<audio bind:this="{audio}" src="timer_done.m4a"></audio>