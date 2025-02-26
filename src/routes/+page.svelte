<script lang="ts">
import { onMount } from 'svelte'
import NumberFlow from '@number-flow/svelte'

let counter = $state(0)

onMount(() => {
	const interval = setInterval(() => {
		counter += 1
	}, 1000)

	return () => clearInterval(interval)
})
</script>

<NumberFlow
	value={counter}
	prefix="$"
  format={{
    style: 'decimal',
    minimumFractionDigits: 2,
    maximumFractionDigits: 2
  }}
/>
