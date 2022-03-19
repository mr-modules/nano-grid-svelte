<script>
  import { beforeUpdate } from "svelte";

  export let className = "",
    width = "";

  let computedWidth, classes;
  beforeUpdate(() => {
    computedWidth = width !== "" ? `sz${width}` : "";
    classes = ["container", className, computedWidth]
      .join(" ")
      .replace(/\s+/g, " ")
      .trim();
  });
</script>

<template>
  <div class={classes}>
    <slot />
  </div>
</template>
