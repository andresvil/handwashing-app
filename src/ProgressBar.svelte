<script>
    export let progressPercent;
</script>

<style>
    .progress-container {
        margin: 20px 0;
        border: solid #a3a3a3 1px;
    }

    .progress-bar {
        height: 30px;
        background-color: springgreen;
    }
</style>

<div bp="grid">
    <div class="progress-container" bp="offset-5@md 4@md 12@sm">
        <div class="progress-bar" style="width: {progressPercent}%;">
            <span class="sr-only">{progressPercent}%</span>
        </div>
    </div>
</div>