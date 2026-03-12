<script lang="ts">
  // Import the component
  import { TextArea } from "../lib/index.ts";

  // The value we want to transmit to the textarea
  let message = $state<string>("Hello, here is The Prime Builder");
</script>

<div>
  <h1>Demo of<br /> @theprimebuilder/textarea</h1>
  <TextArea value={message} class="textarea" placeholder={"Type something"} />
</div>

<style>
  div {
    box-sizing: border-box;
    width: 100%;
    min-height: 100dvh;
    margin-inline: auto;
    display: flex;
    flex-direction: column;
    justify-content: center;
    align-items: center;
    row-gap: var(--s-large);
  }

  h1 {
    font-size: var(--header);
    color: var(--primary);
  }
  /* Declarig a global style with a specific style to target our textarea */
  :global(.textarea) {
    box-sizing: border-box;
    max-width: 90%;
    max-height: 50dvh;
    font-size: var(--body);
    padding: var(--p-small);
    border-radius: var(--r-small);
    overflow-x: hidden;
    overflow-y: auto;

    /* Scrollbar hiding optional */
    &::-webkit-scrollbar {
      display: none;
    }
    scrollbar-width: none;
    -ms-overflow-style: none;
  }

  @media screen and (min-width: 650px) {
    :global(.textarea) {
      max-width: 50%;
    }
  }
</style>
