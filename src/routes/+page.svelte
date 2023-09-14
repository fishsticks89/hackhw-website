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
    let width: number;
    let height: number;
    let scroll: number;

    $: showbuttons = height < width;

    let info: HTMLElement;
</script>

<svelte:window bind:innerWidth={width} bind:innerHeight={height} />

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

{#if showbuttons}
    <div
        class="buttons"
        style={`
        position: fixed;
        bottom: 6px;
        left: 50%;
        transform: translateX(-50%);
        background-color: #000000cc;
        border-radius: 10px;
    `}
    >
        <button
            id="join"
            class="dobuttons"
            on:click={() => {
                window.location.href =
                    "https://bsf8x7mgm2l.typeform.com/to/xOLsX7CJ";
            }}>Join Now</button
        >
        <button
            id="learn"
            class="dobuttons"
            on:click={() => {
                info.scrollIntoView({ behavior: "smooth" });
            }}>Learn More</button
        >
    </div>
{/if}
<div class="body">
    <p>
        Welcome to HackHW's Game Jam – a 48-hour programming marathon judged by
        a panel of alumni in tech
    </p>
    <div class="buttons">
        <button
            id="join"
            class="dobuttons"
            on:click={() => {
                window.location.href =
                    "https://bsf8x7mgm2l.typeform.com/to/xOLsX7CJ";
            }}>Join Now</button
        >
        <button
            id="learn"
            class="dobuttons"
            on:click={() => {
                info.scrollIntoView({ behavior: "smooth" });
            }}>Learn More</button
        >
    </div>
    <img class="sponsor-thank" src="/sponsor-thank.svg" alt="" srcset="" />
    <div class="sponsors">
        <!-- wolfram, xyz, sticker-mule, onepassword, codecrafters -->
        <img class="sponsor" src="/sponsors/wolfram.png" alt="" srcset="">
        <img class="sponsor" src="/sponsors/xyz.png" alt="" srcset="">
        <img class="sponsor" src="/sponsors/sticker-mule.jpeg" alt="" srcset="">
        <img class="sponsor" src="/sponsors/onepassword.png" alt="" srcset="">  
        <img class="sponsor" src="/sponsors/codecrafters.png" alt="" srcset="">
    </div>
    <img bind:this={info} class="info" src={width > (height / 3) + 500 ? "/info.svg" : "/info-thin.svg"} alt="" srcset="" />
</div>

<style>
    .info {
        margin-top: 50px;
        width: 100%;
    }
    .sponsor {
        height: 100px;
        margin: 20px;
    }
    .sponsors {
        display: flex;
        flex-wrap: wrap;
        justify-content: center;
        align-items: center;
        margin-top: 50px;

    }
    .sponsor-thank {
        position: relative;
        left: 50%;
        transform: translateX(-50%);

        margin-top: calc(70px + 3vh);
        width: calc(15rem + 3vmin);
    }
    .dobuttons {
        border: 0px;
        border-radius: 10px;
        height: 50px;
        width: 180px;
        font-family: "Roboto-Medium", monospace;
        font-size: 14px;
        margin: 10px;
        cursor: pointer;

        color: black;

        max-width: 35vw;
    }
    #join {
        background-color: #ededed;
    }
    #learn {
        background-color: black;
        color: #dbdbdb;
        content: "Learn More";

        border-width: 2px;
        border-style: solid;
        border: 2px solid;

        border: 1px solid #ff63c6;
    }

    .buttons {
        width: fit-content;
        margin: auto;
        margin-top: 25px;

        display: flex;
        flex-wrap: wrap;
        justify-content: center;
        align-items: center;
    }

    p {
        font-family: "Inter-SemiBold", monospace;
        font-size: calc(1.3rem + 0.3vw);
        line-height: 150%;

        color: #9a9a9a;
        text-align: center;
        margin: 0px;
        padding: 0px;
    }

    .body {
        padding-bottom: 50vh;
        width: 85%;
        max-width: 2000px;
        display: block;
        margin: auto;
        margin-top: calc(20px + 2vh);
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
