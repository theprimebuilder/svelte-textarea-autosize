# Svelte textarea auto size
A lightweight Svelte component to get a textarea that automatically adjusts its height.

![Svelte](https://img.shields.io/badge/Svelte-5-ff3e00?logo=svelte&logoColor=white)
![TypeScript](https://img.shields.io/badge/TypeScript-007ACC?logo=typescript&logoColor=white)
![Bun](https://img.shields.io/badge/Bun-000000?logo=bun&logoColor=white)


**version 1.0.6**

# Warning: only version 1.0.4 is stable

# Installation 

```bash
npm i @theprimebuilder/svelte-textarea-autosize
```
or 

```bash
bun i @theprimebuilder/svelte-textarea-autosize
```
# Information

The Svelte Textarea Auto-size component accepts 3 main props:

1. Value 
- Description: The value are the data (string) type you want to pass to your textarea for modification. It supports Svelte 5 $bindable().

2. Placeholder
- Description: The default text displayed when the textarea is empty.

3. Class
- Description: Used for custom CSS styling.

Additional: It also supports all standard <textarea> attributes (maxlength, disabled, rows, etc.) via rest props. For more information, refer to the [Developper Mozila docs](https://developer.mozilla.org/en-US/docs/Web/HTML/Reference/Elements/textarea)

# Basic usage
```svelte
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

```

## Development

If you want to contribute or test the component locally:

1. Clone the repo: `git clone https://github.com/theprimebuilder/svelte-textarea-autosize.git`

2. Install dependencies: `bun install`

3. Start the dev server: `bun run dev`

Open your browser at `http://localhost:5173` to see the demo page.


# Links
[NPM](https://www.npmjs.com/package/@theprimebuilder/svelte-textarea-autosize)

[Github repo](https://github.com/theprimebuilder/svelte-textarea-autosize)

[Github profile](https://github.com/theprimebuilder)

# Note
If you encounter any issues, please report them on the GitHub repository. Thank you!