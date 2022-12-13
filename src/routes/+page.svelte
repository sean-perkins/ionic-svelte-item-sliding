<script lang="ts">
	import { onMount } from 'svelte';

	let itemSlidingStart: HTMLIonItemSlidingElement;
	const dragEvent = async (event: any) => {
		const openAmount = await itemSlidingStart.getOpenAmount();
		console.log('openAmount', openAmount);
	};

	onMount(() => {
		console.log('itemSliding elementRef', itemSlidingStart);
	});
</script>

<ion-item-sliding on:ionDrag={dragEvent} on:click={dragEvent} bind:this={itemSlidingStart}>
	<ion-item-options side="start">
		<ion-item-option color="primary">Mark Unread</ion-item-option>
	</ion-item-options>

	<ion-item-options side="end">
		<ion-item-option color="danger">Delete</ion-item-option>
	</ion-item-options>

	<ion-item class="blue-item"> ssss </ion-item>
</ion-item-sliding>
