<script>
import ProgressBar from "./ProgressBar.svelte";
let totalSeconds = 20;
let secondLeft = totalSeconds;
let isRunning = false;
$: progress = ((totalSeconds - secondLeft) / totalSeconds) * 100;
function startTimer() {
    const timer = setInterval(() => {
        isRunning = true;
        secondLeft -= 1;
        if (secondLeft == 0) {
            clearInterval(timer);
            isRunning = false;
            secondLeft = totalSeconds;
        }
    }, 1000);
}

</script>
<style>
    h2 {
        margin: 0;
    }
    .start {
        background-color: rgb(180, 80,80);
        width: 100%;
        margin: 10px 0;
    }
    .start[disabled] {
        background-color: gray;
        cursor: not-allowed;
    }
</style>
<div bp="grid">
    <h2
    bp="offset-5@md 4@md 12@sm">
    Seconds left: {secondLeft}
    </h2>
</div>

<ProgressBar {progress}/>
<div bp="grid">
    <button bp="offset-5@md 4@md 12@sm" class="start" on:click={startTimer} disabled={isRunning}>
        Start
    </button>
</div>