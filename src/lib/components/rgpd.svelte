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
		Spacer,
		Tooltip
	} from 'mytril/components';
	import { onMount } from 'svelte';

	let open = $state(false);

	onMount(() => {
		open = true;
	});
</script>

<Dialog bind:open>
	<Card rounded="4xl" background="pink">
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
			<Tooltip label="message tooltip" location="bottom" density="comfortable">
				{#snippet tooltip()}
					<div class="grid">
						<div class="font-bold">Message</div>
						<div>Bla bla bla bla bla licorne de poulet</div>
					</div>
				{/snippet}
				<Btn rounded="pill" onclick={() => (open = true)} background="primary" color="on-primary">
					{capitalize('Big tooltip bottom')}
					{#snippet append()}
						<Icon icon="font:mgc_cookie_line" color="on-primary" />
					{/snippet}
				</Btn>
			</Tooltip>
			<Spacer />
			<Tooltip label="message tooltip" location="right">
				<Btn rounded="pill" onclick={() => (open = true)} background="primary" color="on-primary">
					{capitalize('right')}
					{#snippet append()}
						<Icon icon="font:mgc_cookie_line" color="on-primary" />
					{/snippet}
				</Btn>
			</Tooltip>
			<Tooltip label="message tooltip" location="top" color="white" background="black">
				<Btn rounded="pill" onclick={() => (open = true)} background="primary" color="on-primary">
					{capitalize('top')}
					{#snippet append()}
						<Icon icon="font:mgc_cookie_line" color="on-primary" />
					{/snippet}
				</Btn>
			</Tooltip>
			<Tooltip label="message tooltip" location="bottom">
				<Btn rounded="pill" onclick={() => (open = true)} background="primary" color="on-primary">
					{capitalize('bottom')}
					{#snippet append()}
						<Icon icon="font:mgc_cookie_line" color="on-primary" />
					{/snippet}
				</Btn>
			</Tooltip>
			<Tooltip label="message tooltip" location="left">
				<Btn rounded="pill" onclick={() => (open = true)} background="primary" color="on-primary">
					{capitalize('left')}
					{#snippet append()}
						<Icon icon="font:mgc_cookie_line" color="on-primary" />
					{/snippet}
				</Btn>
			</Tooltip>
		</CardActions>
	</Card>
</Dialog>
