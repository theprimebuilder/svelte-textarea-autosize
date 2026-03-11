<script lang="ts">
  // Getting the textarea
  let textAreaElement: HTMLTextAreaElement | undefined = $state();
  // Declaring value with svelte bindable and ...rest to get textarea property
  let { value = $bindable(""), ...rest } = $props();

  /* resize function get the actual */
  function resize() {
    if (!textAreaElement) return;
    (textAreaElement.style.height = "auto"),
      (textAreaElement.style.height = `${textAreaElement.scrollHeight}px`);
  }
  // Using effect to resize the textarea when value change
  $effect(() => {
    const _ = value;
    resize();
  });
</script>

<textarea
  class="textarea resize-ta"
  {...rest}
  bind:this={textAreaElement}
  bind:value
  rows="1"
></textarea>

<style>
  textarea {
    display: block;
    width: 100%;
    overflow: hidden;
    resize: none;
  }
</style>
