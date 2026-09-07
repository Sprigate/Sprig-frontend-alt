<script lang='ts'>
      import type {Snippet} from 'svelte';

      interface Props {
            // terbuka atau tidak?
            isOpen: boolean;

            // judul popup
            title?: string;

            // isi/konten dari popup
            children: Snippet;

            // what should it do kalau popup close?
            onClose: () => void;
      }

      let {
            isOpen = $bindable(false),
            title,
            children,
            onClose
      }: Props = $props();

      let dialogElement: HTMLDialogElement | null = $state(null);

      //open & close popup reactively
      $effect(() => {
            const dialog = dialogElement;
            if (!dialog) return;

            if (isOpen && !dialog.open) {
                  dialog.showModal();
            } else if (!isOpen && dialog.open) {
                  dialog.close()
            }
      });

      function handleClose(){
            isOpen = false
            onClose?.();
      }
</script>

<dialog bind:this={dialogElement} onclose={handleClose} class="modal">
      <div class="modal-box">
            {#if title}
                  <h3 class="text-lg font-bold mb-4">{title}</h3>
            {/if}

            {@render children?.()}

            <div class="modal-action">
                  <form method="dialog">
                        <button class="btn btn-ghost">Close</button>
                  </form>
            </div>
      </div>
      <form method="dialog" class="modal-backdrop">
            <button onclick={handleClose}>Close</button>
      </form>
</dialog>