<script lang="ts">
  import { Button } from "$lib/components/ui/button";
  import { Sun, Moon } from "radix-icons-svelte";
  import { toggleMode, mode } from "mode-watcher";
</script>

<h1 class="pt-10 text-4xl font-semibold text-center text-black dark:text-white">
  Svelte {#if $mode === undefined}Toggle
  {:else}
    {$mode}
  {/if} Mode
</h1>

<div class="flex items-center justify-center pt-6">
  <Button on:click={toggleMode} variant="outline" size="icon">
    <Sun
      class="h-[1.2rem] w-[1.2rem] rotate-0 scale-100 transition-all dark:-rotate-90 dark:scale-0"
    />
    <Moon
      class="absolute h-[1.2rem] w-[1.2rem] rotate-90 scale-0 transition-all dark:rotate-0 dark:scale-100"
    />
    <span class="sr-only">Toggle theme</span>
  </Button>
</div>
