<template>
  <footer
    v-if="$nav.currentLayout !== 'cover'"
    class="absolute bottom-0 right-0 p-2"
  >
    <small>{{ $nav.currentPage }} / {{ $nav.total }}</small>
  </footer>
</template>