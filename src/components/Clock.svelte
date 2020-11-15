<script>
    import { DateTime } from "luxon";
    import { onMount } from "svelte";

    let date = DateTime.local().toLocaleString(DateTime.DATE_SHORT);
    let time = DateTime.local().toLocaleString(DateTime.TIME_24_SIMPLE);

    onMount(() => {
        const interval = setInterval(() => {
            date = DateTime.local().toLocaleString(DateTime.DATE_SHORT);
            time = DateTime.local().toLocaleString(DateTime.TIME_24_SIMPLE);
        }, 1000);

        return () => {
            clearInterval(interval);
        };
    });
</script>

<div class="clock">
    <div class="time">
        {time}
    </div>
    <div class="date">
        {date}
    </div>
</div>

<style>
    .clock{
        color: #FFFFFF;
        font-size: small;

    }
    .time, .date{
        padding: 0 0.5rem;
        margin: 0;
        line-height: normal;
        text-align: center;
        user-select: none;
    }
</style>