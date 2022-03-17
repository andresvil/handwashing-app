<script>
    import ProgressBar from "./ProgressBar.svelte";

    const totalSeconds = 20;
    let secondsLeft = totalSeconds;
    $: progressPercent = ((totalSeconds-secondsLeft)/totalSeconds) * 100;

    let isRunning = false;
    function startTimer() {
        isRunning = true;
        const timer = setInterval(() => {
        secondsLeft--;
        if (secondsLeft === 0) {
            clearInterval(timer);
            isRunning = false;
            secondsLeft = totalSeconds;
        }
    }, 1000);
    }
</script>

<style>
    h2 {
        margin: 0;
    }

    .start {
        background-color: #6495ed;
        margin: 10px 0;
        width: 100%;
    }

    .start[disabled] {
        background-color: #6494ed7c;
        cursor: not-allowed;
    }
</style>

<div bp="grid">
    <h2 bp="offset-5@md 4@md 12@sm">Seconds Left: {secondsLeft}</h2>
    
</div>

<ProgressBar {progressPercent} />

<div bp="grid">
    <button class="start" disabled="{isRunning}" on:click="{startTimer}" bp="offset-5@md 4@md 12@sm">
        Start
    </button>
</div>




