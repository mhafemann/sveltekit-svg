<script lang="ts">
    export let paths: string[],
                ariaHidden: boolean = true,
                url: string | undefined = undefined,
                label: string = '';
</script>
  
<svelte:element
    this={url ? 'a' : 'span'}
    href={url || null}
    aria-label={url ? url : 'none'}>
    <svg
      role={ariaHidden ? '' : 'img'}
      aria-hidden={ariaHidden}
      xmlns="http://www.w3.org/2000/svg"
      fill="none"
      viewBox="0 0 24 24"
      stroke="currentColor">
      {#if !ariaHidden}
        <title>{label}</title>
      {/if}
    {#each paths as path}
        <path stroke-linecap="round" stroke-linejoin="round" d={path} />
    {/each}
    </svg>
</svelte:element>