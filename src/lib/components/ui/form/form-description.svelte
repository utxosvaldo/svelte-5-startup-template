<script lang="ts">
	import * as FormPrimitive from "formsnap";
	import type { HTMLAttributes } from "svelte/elements";
	import { cn } from "$lib/utils.js";

	type $$Props = HTMLAttributes<HTMLSpanElement>;
	interface Props {
		class?: string | undefined | null;
		children?: import('svelte').Snippet<[any]>;
		[key: string]: any
	}

	let { class: className = undefined, children, ...rest }: Props = $props();
	
</script>

<FormPrimitive.Description
	class={cn("text-muted-foreground text-sm", className)}
	{...rest}
	
>
	{#snippet children({ descriptionAttrs })}
		{@render children?.({ descriptionAttrs, })}
	{/snippet}
</FormPrimitive.Description>
