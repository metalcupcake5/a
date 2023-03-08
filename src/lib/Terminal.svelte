<script lang="ts">
    import { onMount } from "svelte";
    export let text: string;
    let display: string[] = [];
    let index = 0;
    let clear: any;
    let updateText = () => {
        display = [...display, text[index]];
        index++;
    };
    $: if (index < text.length) {
        clearInterval(clear);
        clear = setInterval(updateText, 1);
    }
</script>

<span style="white-space: pre-wrap;">{@html display.join("")}</span>
