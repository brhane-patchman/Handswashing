<script>
import ProgressBar from "./ProgressBar.svelte";
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
</style>
<div bp="grid">
    <h2
    bp="offset-5@md 4@md 12@sm">
    Seconds left:
    </h2>
</div>

<ProgressBar/>

<button class="start">
    Start
</button>