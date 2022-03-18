<script>
  import { beforeUpdate } from "svelte";

  export let horizontal = true,
    vertical = true,
    color = "transparent";

  let computedHorizontal = !horizontal ? "no-horizontal" : "";
  let computedVertical = !vertical ? "no-vertical" : "";

  let computedClasses, computedLabel;

  beforeUpdate(() => {
    computedClasses = [
      "scroll-area",
      color,
      computedHorizontal,
      computedVertical,
    ]
      .join(" ")
      .replace(/\s+/g, " ")
      .trim();
  });
</script>

<template>
  <div on:scroll|passive class={computedClasses}>
    <slot />
  </div>
</template>
