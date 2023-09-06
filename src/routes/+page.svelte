<script lang="ts">
    import { browser } from "$app/environment";
    import { onMount } from "svelte";
    import Bouncy from "./../lib/bouncy.svelte";
    let stout = false;

    // let scrollw = 0;
    // let normalw = 0;

    // const checkScrollBars = () => {
    //     if (!browser) {
    //         console.log("skipping");
    //         return;
    //     }
    //     const b = document.body;

    //     normalw = window.innerWidth;
    //     scrollw = normalw - b.clientWidth;
    //     console.log(scrollw);
    // };
    // onMount(() => {
    //     checkScrollBars();
    //     console.log("mounted");
    // });
    // if (browser) window.onresize = checkScrollBars;
</script>

{#if stout}
    <Bouncy />
{/if}
<img class="logo" src="/whole-logo.svg" alt="logo" srcset="" />
<div class="nav">
    <button
        class="schedule-button"
        on:click={() => {
            alert("no schedule yet");
        }}
    >
        <img src="/schedule-button.svg" class="schedule-icon" alt="" />
    </button>
    <button
        class="menu-button"
        on:click={() => {
            stout = !stout;
        }}
    >
        <img src="/menu-button.svg" class="menu-icon" alt="" />
    </button>
</div>
<img class="bkg" src="/bkg.png" alt="" />

<div class="body">
    <p>
        Welcome to HackHW's Game Jam – a 48-hour programming marathon judged by
        a panel of alumni in tech
    </p>
</div>

<style>
    p {
        font-family: "Inter-SemiBold", monospace;
        font-size: 1.3rem;
        color: #9a9a9a;
        text-align: center;
        margin: 0px;
        padding: 0px;
    }

    .body {
        margin-top: 30px;

        height: 100vh;
        width: 85%;
        max-width: 80vh;
        display: block;
        margin: auto;
    }

    .schedule-icon {
        height: 100%;
    }
    .schedule-button {
        height: 45px;
        background-color: transparent;
        padding: 0px;

        border: 0px solid transparent;

        margin-right: 7px;
    }
    .menu-icon {
        width: 100%;
        height: 100%;
    }
    .menu-button {
        width: 45px;
        height: 45px;
        margin-inline: 7px;

        border-radius: 100%;
        border: 0px;

        background-color: transparent;

        padding: 0px;
    }
    .nav {
        top: 0px;
        right: 0px;
        height: 60px;
        width: 100vw;

        position: fixed;

        display: flex;
        align-items: center;
        justify-content: right;
    }
    .logo {
        left: 0px;
        top: 0px;
        position: fixed;
        width: 40vw;
        max-width: 170px;
    }
    .bkg {
        margin-top: 30px;
        width: 100%;
        box-shadow: inset 0 0 0 2000px rgb(0, 0, 0);
    }
</style>
