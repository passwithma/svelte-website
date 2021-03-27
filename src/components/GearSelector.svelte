<script>
    import { createEventDispatcher } from 'svelte';
    let dispatch = createEventDispatcher();

    export let items;
    export let activeItem;
    
</script>

<div class="wrapper">
    <ul>
        {#each items as item}
            <li on:click={() => dispatch('tabChange', item)}>
                <div class="slider" class:A={item === activeItem && activeItem === "Automatic"} class:M={item === activeItem && activeItem === "Manual"}>{item}</div>
            </li>
        {/each}
    </ul>
</div>

<style>

    .wrapper {
        display:flex;
        width: 100%;
        text-align: center;
        justify-content: center;
    }

    .slider {
        border: 2px solid black;
        border-radius: 5px;
        cursor: pointer;
        padding: 5px;
        margin: 2px;
        color: #9A9B9C;
    }

    ul {
        display: inline-flex;
        padding: 0;
        list-style-type: none;
        margin: 1px;
    }

	li {
		display: block;
		justify-content: left;
        cursor: pointer;
        padding: 5px;
        font-size: 18px;
	}

    .M {
        color: #981E32;
    }

    .A {
        color: #2e75b6;
    }

</style>