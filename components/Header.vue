<template>
  <header class="header-bar">
    <SortControls />
    <FilterControls />
    <SearchBox />
  </header>
</template>

<script>
import SortControls from './SortControls.vue';
import FilterControls from './FilterControls.vue';
import SearchBox from './SearchBox.vue';
export default { components: { SortControls, FilterControls, SearchBox } }
</script>