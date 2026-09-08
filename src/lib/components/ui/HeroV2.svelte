<script lang="ts">
      import heroBG from '$lib/assets/heroBackground2.png'
      import type { Snippet } from 'svelte'

      interface Props {
            children: Snippet;
      }

      let { children }: Props = $props();

</script>

<div class="hero min-h-80" style="background-image: url({heroBG}); background-position: center;">
      <div class="hero-overlay"></div>
      <div class="hero-content text-neutral-content text-center">
            <div class="max-w-lg">
                  {@render children()}
            </div>
      </div>
</div>