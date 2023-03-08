<script lang="ts">
    import { base } from "$app/paths";
    import Terminal from "$lib/Terminal.svelte";
    import icon from "../assets/cat_hoodie_cropped.jpg";

    let text = `metal@cupcake 
-----------------------
your local transfemme idiot
she/they
trans enby demigirl
student, programmer, programmer student

links(click)
pronounce
hub of gits
moosic`;

    let display: string[] = [];
    let typing = true;
    let index = 0;
    let clear: any;
    let updateText = () => {
        display = [...display, text[index]];
        index++;
    };
    $: if (index < text.length) {
        clearInterval(clear);
        clear = setInterval(updateText, 5);
    } else {
        typing = false;
    }
</script>

<main>
    <p>/meow/home > nyafetch</p>
    <div class="flex">
        <a
            href="https://www.pixiv.net/en/artworks/101936708"
            title="View image source"
            ><img class="icon" src={icon} alt="avatar" /></a>
        <div>
            {#if typing}
                <span style="white-space: pre-wrap;">{display.join("")}</span>
            {:else if !typing}
                <!-- prettier-ignore -->
                <span id="desc">
                    metal@cupcake 
                    -----------------------
                    your local transfemme idiot
                    <a href="https://en.pronouns.page/@metalcupcake5">she/they</a>
                    trans enby demigirl
                    student, programmer, programmer student
                    
                    links(click)
                    <a href="https://en.pronouns.page/@metalcupcake5">pronounce</a><br>
                    <a href="https://github.com/metalcupcake5">hub of gits</a><br>
                    <a href="https://www.last.fm/user/metalcupcake5">moosic</a><br>
                    <a href="https://twitter.com/metalcupcake5">bird app</a><br>
                </span>
            {/if}
        </div>
    </div>
    <p>/meow/home > <span class="cursor">█</span></p>
</main>

<style>
</style>
