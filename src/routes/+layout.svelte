<script lang="ts">
  import { page } from '$app/stores'

  const siteName = 'FMS'
</script>

<!--
  @component

-->

<svelte:head>
  {#if $page.data.meta?.title}
    <title>{$page.data.meta?.title} — {siteName}</title>
  {:else}
    <title>{siteName}</title>
  {/if}
</svelte:head>

<div>
  <slot />
</div>

<style lang="scss">
  :global {
    :root {
      // FONTS
      --fonts-sans: Mulish, -apple-system, BlinkMacSystemFont, "Segoe UI", Roboto, "Helvetica Neue", Arial, sans-serif;
      --fonts-monospace: "IBM Plex Sans Mono", "Source Code Pro", Menlo, Monaco, Consolas, "Liberation Mono", "Courier New", monospace;
      --weight-light: 175;
      --weight-normal: 300;
      --weight-semibold: 450;
      --weight-bold: 600;
      // stylelint-enable stylistic/max-line-length,value-keyword-case
      // COLOURS
      --colour-black: hsl(0deg 0% 4%);
      --colour-white: hsl(0deg 0% 95%);
      --colour-light-grey: hsl(0deg 0% 71%);
      --colour-mid-grey: hsl(0deg 0% 50%);
      --colour-dark-grey: hsl(0deg 0% 25%);
      // SITE ELEMENTS
      --colour-background: var(--colour-white);
      --colour-foreground: var(--colour-black);
      --colour-focus-ring: hsl(45deg 85% 79%);
      --colour-input-border: var(--colour-dark-grey)
    }

    @font-face {
      font-family: Mulish;
      font-style: normal;
      font-weight: 100 900;
      src: url("/fonts/mulish-variable.woff2") format("woff2 supports variations"), url("/fonts/mulish-variable.woff2") format("woff2-variations");
      font-display: swap;
    }

    @font-face {
      font-family: Mulish;
      font-style: italic;
      font-weight: 100 900;
      src: url("/fonts/mulish-italic-variable.woff2") format("woff2 supports variations"), url("/fonts/mulish-italic-variable.woff2") format("woff2-variations");
      font-display: swap;
    }

    // Based on minireset.css v0.0.6 | MIT License | github.com/jgthms/minireset.css
    html,
    body,
    p,
    ol,
    ul,
    li,
    dl,
    dt,
    dd,
    blockquote,
    figure,
    fieldset,
    legend,
    textarea,
    pre,
    iframe,
    hr,
    h1,
    h2,
    h3,
    h4,
    h5,
    h6 {
      padding: 0;
      margin: 0;
      color: var(--colour-foreground);
    }

    h1,
    h2,
    h3,
    h4,
    h5,
    h6 {
      font-weight: var(--weight-bold);
    }

    h1 {
      margin-bottom: 1.5rem;
      font-size: 2.5rem;
    }

    h2 {
      margin-top: 1.5rem;
      margin-bottom: 1rem;
      font-size: 1.75rem;
    }

    h3 {
      margin-bottom: 1.6rem;
      font-size: 1.6rem;
    }

    h4 {
      margin-bottom: 1.4rem;
      font-size: 1.4rem;
    }

    h5 {
      margin-bottom: 1.2rem;
      font-size: 1.2rem;
    }

    h6 {
      margin-bottom: 1rem;
      font-size: 1rem;
    }

    p {
      margin-bottom: 1rem;
    }

    ul {
      list-style: none;
    }

    button,
    input,
    select {
      margin: 0;
      font-family: var(--fonts-sans);
      font-size: 1rem;
      font-weight: var(--weight-normal);
    }

    pre,
    code {
      font-family: var(--fonts-monospace);
    }

    b,
    strong {
      font-weight: var(--weight-bold);
    }

    html {
      box-sizing: border-box;
    }

    * {
      box-sizing: inherit;

      &::before,
      &::after {
        box-sizing: inherit;
      }

      &:focus {
        outline: none;
        box-shadow: none;
      }

      &:focus-visible {
        outline: none;
        box-shadow: 0 0 2px 4px var(--colour-focus-ring);
      }
    }

    img,
    video {
      max-width: 100%;
      height: auto;
    }

    iframe {
      border: 0;
    }

    table {
      border-spacing: 0;
      border-collapse: collapse;
    }

    td,
    th {
      padding: 0;
    }

    ul,
    ol {
      margin-right: 1rem;
      margin-left: 1.5rem;

      li {
        padding-left: 0.5rem;
      }
    }

    input,
    textarea {
      border: 1px solid var(--colour-input-border);

      &:focus {
        border-color: transparent;
      }
    }

    body {
      font-family: var(--fonts-sans);
      font-weight: var(--weight-normal);
      line-height: 1.5;
      background-color: var(--colour-background);
    }

    a {
      color: var(--colour-link);
      text-decoration: none;

      &:hover {
        color: var(--colour-hover);
        text-decoration: underline;
      }
    }
  }
</style>
