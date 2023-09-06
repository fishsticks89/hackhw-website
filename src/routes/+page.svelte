<script lang="ts">
    import Bouncy from "./../lib/bouncy.svelte";
    let stout = true;
</script>

{#if stout}
    <Bouncy />
{/if}
<img class="logo" src="/whole-logo.svg" alt="logo" srcset="" />
<img class="bkg" src="/bkg.png" alt="" />
<!-- a fixed bottom white bar with black top outline with button to sign up -->
<div class="bottom-bar">
    <div class="p-2">
        <button
            class="btn"
            on:click={() => {
                window.location.href =
                    "https://bsf8x7mgm2l.typeform.com/to/xOLsX7CJ";
            }}>RSVP</button
        >
    </div>
</div>

<style>
    .logo {
        left: 0px;
        top: 0px;
        position: fixed;
        width: 20vw;
        max-width: 170px;
    }
    .bkg {
        width: 100%;
        box-shadow: inset 0 0 0 2000px rgb(0, 0, 0);
    }
    .btn {
        border-radius: 0;
        border-color: black;
        max-height: 10vw;
        height: 5vh;
        width: calc(20px + 10vw);
    }
    .bottom-bar {
        position: fixed;
        padding: 20px;
        bottom: 20px;
        width: calc(100% - 80px);
        left: 20px;
        max-width: calc(120vh - 80px);
        border-color: white;
        display: flex;
        justify-content: right;
        align-items: center;
        /* makes background b&w checkerboard */
        background: repeating-conic-gradient(#ffffffc9 0% 25%, #233739 0% 50%)
            50% / 20px 20px;

        z-index: 5000;
    }
</style>
