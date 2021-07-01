<template>
  <svg class="icon">
    <use :xlink:href="'#'+name"></use>
  </svg>
</template>

<script lang="ts">

let importAll = (requireContext: ReturnType<typeof require.context>) => requireContext.keys().forEach(requireContext);
importAll(require.context('../assets/icons', true, /\.svg$/));

export default {
  props: ['name'],
  name: 'Icon'
};
</script>

<style lang="scss" scoped>
.icon {
  vertical-align: -0.15em;
  fill: black;
}
</style>