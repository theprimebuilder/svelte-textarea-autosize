<script lang="ts">
  import type { HTMLTextareaAttributes } from "svelte/elements";

  // Getting the textarea
  let textAreaElement: HTMLTextAreaElement | undefined = $state();

  interface TextAreaProps extends HTMLTextareaAttributes {
    value?: string;
    class?: string;
  }

  // Declaring value with svelte bindable and ...rest to get textarea property
  let {
    value = $bindable(""),
    class: className = "",
    ...rest
  }: TextAreaProps = $props();

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
  {...rest}
  bind:this={textAreaElement}
  bind:value
  class="textarea-autosize {className}"
  rows="1"
></textarea>

<style>
  .textarea-autosize {
    display: block;
    width: 100%;
    overflow: hidden;
    resize: none;
    box-sizing: border-box;
  }
</style>
