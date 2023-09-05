<script lang="ts">
    import { create } from "canvas-confetti";
    let canvas: HTMLCanvasElement;
    let canvas2: HTMLCanvasElement;
    let myConfetti: any;
    let myConfetti2: any;
    setTimeout(() => {
        myConfetti = create(canvas, {
            resize: true,
            useWorker: true,
        });
        myConfetti2 = create(canvas2, {
            resize: true,
            useWorker: true,
        });
    });
</script>

<canvas bind:this={canvas2} />
<!-- svelte-ignore a11y-click-events-have-key-events -->
<!-- svelte-ignore a11y-no-noninteractive-element-interactions -->
<!-- svelte-ignore a11y-no-static-element-interactions -->
<div
    class="bouncy"
    on:click={() => {
        myConfetti({
            particleCount: 100,
            spread: 160,
            // any other options from the global
            // confetti function
        });
        setTimeout(() => {
            myConfetti2({
                particleCount: 100,
                spread: 160,
                // any other options from the global
                // confetti function
            });
        }, 1000);
    }}
>
    <canvas bind:this={canvas} />
    <img src="/stout.jpg" alt="stout" srcset="" />
    <p>click me!</p>
</div>

<style>
    canvas {
        position: absolute;
        z-index: 2000;

        width: 100%;
        height: 100%;
    }
    p {
        background-color: white;
        position: absolute;
        top: 20px;
    }
    /* vanilla css dvd-style bouncing animation */
    img {
        width: 100%;
        height: 100%;
    }
    .bouncy {
        display: block;
        position: absolute;
        width: calc(90px + 10vmin);
        height: calc(90px + 10vmin);
        -webkit-animation: moveX 2s linear 0s infinite alternate,
            moveY 3.4s linear 0s infinite alternate;
        -moz-animation: moveX 2s linear 0s infinite alternate,
            moveY 3.4s linear 0s infinite alternate;
        -o-animation: moveX 2s linear 0s infinite alternate,
            moveY 3.4s linear 0s infinite alternate;
        animation: moveX 2s linear 0s infinite alternate,
            moveY 3.4s linear 0s infinite alternate;
    }

    @-webkit-keyframes moveX {
        from {
            left: 0;
        }
        to {
            left: calc(100vw - (90px + 10vmin));
        }
    }
    @-moz-keyframes moveX {
        from {
            left: 0;
        }
        to {
            left: calc(100vw - (90px + 10vmin));
        }
    }
    @-o-keyframes moveX {
        from {
            left: 0;
        }
        to {
            left: calc(100vw - (90px + 10vmin));
        }
    }
    @keyframes moveX {
        from {
            left: 0;
        }
        to {
            left: calc(100vw - (90px + 10vmin));
        }
    }

    @-webkit-keyframes moveY {
        from {
            top: 0;
        }
        to {
            top: calc(100vh - (120px + 10vmin));
        }
    }
    @-moz-keyframes moveY {
        from {
            top: 0;
        }
        to {
            top: calc(100vh - (120px + 10vmin));
        }
    }
    @-o-keyframes moveY {
        from {
            top: 0;
        }
        to {
            top: calc(100vh - (120px + 10vmin));
        }
    }
    @keyframes moveY {
        from {
            top: 0;
        }
        to {
            top: calc(100vh - (120px + 10vmin));
        }
    }
</style>
