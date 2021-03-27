<script>

    export let photo;
    export let text;
    export let activeGearItem;

    let flipped = false;

</script>

{#if flipped}
    <div class:A={activeGearItem === "Automatic"} class:M={activeGearItem === "Manual"} class="container" on:click={() => flipped = !flipped}>
        <p>{text}</p>
    </div>
{:else}
    <div class:A={activeGearItem === "Automatic"} class:M={activeGearItem === "Manual"} class="container" style="--image: url(/images/{photo});" on:click={() => flipped = !flipped}>
    </div>
{/if}

<style>

    .container {
        border: 2px solid black;
        box-shadow: 3px 3px 3px 3px rgba(152, 30, 50, .4);
        border-radius: 10px;
        background-image: var(--image);
        background-size: cover;
        background-repeat: no-repeat;
        background-position: center;
        max-width: 100%;
        max-height: 100%;
        height: 300px;
        display: flex;
        justify-content: center;
        align-items: center;
        position: relative;
        cursor: pointer;
    }

    @media(max-width:1200px) {
        .container {
            height: 500px;
            width: 450px;
        }
    }

    .M {
        box-shadow: 3px 3px 3px 3px #981E32;
    }

    .A {
        box-shadow: 3px 3px 3px 3px #2e75b6;
    }

    p {
        color: black;
        font-size: 15px;
        text-align:center;
        position: absolute;
        padding: 2px;
    }

    @media(max-width:500px) {
        .container {
            height: 300px;
            width: 275px;
        }
        p {
            font-size: 12px;
        }
    }

</style>