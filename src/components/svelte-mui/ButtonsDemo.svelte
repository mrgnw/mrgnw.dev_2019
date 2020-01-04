<div class="counter">
	{#if counter > 0}{counter}
	{:else}click one
	{/if}
</div>

<Button color="primary" title="Simple button" on:click={increment}>Button</Button>

<Button color="accent" on:click={increment}>
    <!-- left icon -->
    <!-- <Icon path={cartOutline} style="margin: 0 8px 0 -4px;" /> -->
    Add
</Button>

<Button color='#00796b' on:click={increment}>
    Send
    <!-- right icon -->
    <Icon path="M2.01 21L23 12 2.01 3 2 10l15 2-15 2z" style="margin: 0 -4px 0 8px;" />
</Button>


<script>
    import { Button, Icon } from 'svelte-mui/src';
    // import { cartOutline, search } from '/components/icons';
    // import approval from '/components/icons/svg/approval.svg';

    let counter = 0;

    function increment() {
        counter += 1;
    }
</script>

<style>
.counter{
	width: 5em;
	display: inline-block;
	text-align: center;
}
</style>