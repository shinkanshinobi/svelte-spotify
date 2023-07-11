<script lang="ts">
	export let element: 'button' | 'a';
	export let variant: 'solid' | 'outline' | 'danger' = 'solid';
	export let className: string = '';
</script>

<!-- svelte-ignore a11y-no-static-element-interactions -->
<svelte:element
	this={element}
	on:click
	class="button button-{variant} {className}"
	{...$$restProps}
>
	<slot />
</svelte:element>

<style lang="scss">
	.button {
		display: inline-block;
		border: none;
		font-weight: 600;
		font-size: functions.toRem(14);
		border-radius: 20px;
		cursor: pointer;
		padding: 7px 15px;
		text-decoration: none;
		&.button-solid {
			background-color: var(--accent-color);
			color: #000;
			border: 2px solid var(--accent-color);
		}
	}
</style>
