<script lang="ts">
	import { capitalize } from 'mytril/actions';
	import {
		Btn,
		Card,
		CardActions,
		CardText,
		CardTitle,
		Dialog,
		Icon,
		Spacer
	} from 'mytril/components';
	import { onMount } from 'svelte';

	let open = $state(false);

	onMount(() => {
		open = true;
	});
</script>

<Dialog bind:open>
	<Card rounded="4xl">
		<CardActions>
			<Spacer />
			<Btn rounded="pill" onclick={() => (open = false)} size="sm" variant="text"
				>{capitalize('nop')}</Btn
			>
		</CardActions>
		<CardTitle><strong>{capitalize('title')}</strong></CardTitle>
		<CardText>
			<p>{capitalize('balbalabalablaba')}</p>
		</CardText>
		<CardActions class="!mb-2">
			<Spacer />
			<Btn rounded="pill" onclick={() => (open = true)} background="primary" color="on-primary">
				{capitalize('accept')}
				{#snippet append()}
					<Icon icon="font:mgc_cookie_line" color="on-primary" />
				{/snippet}
			</Btn>
		</CardActions>
	</Card>
</Dialog>
