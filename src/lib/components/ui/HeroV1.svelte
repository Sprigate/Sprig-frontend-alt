<script lang="ts">
      import heroBG from '$lib/assets/heroBackground.png'
      import type { Snippet } from 'svelte'

      interface Props {
            children: Snippet;
      }

      let { children }: Props = $props();

</script>

<div class="hero min-h-80" style="background-image: url({heroBG}); background-position: center;">
      <div class="hero-overlay"></div>
      <div class="hero-content text-neutral-content text-center min-w-50 justify-start">
            <div class="max-w-lg">
                  {@render children()}
            </div>
      </div>
</div>