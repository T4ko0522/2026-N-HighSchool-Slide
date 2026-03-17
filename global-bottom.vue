<template>
  <DottedSurface :speed="0.01" :amplitude="40" :frequency-x="0.3" :frequency-y="0.5" />

  <!-- Corner accent lines -->
  <div class="absolute top-0 left-0 w-16 h-16 pointer-events-none" style="z-index: 1">
    <div class="absolute top-4 left-4 w-8 h-px" style="background: rgba(255, 255, 255, 0.12)" />
    <div class="absolute top-4 left-4 w-px h-8" style="background: rgba(255, 255, 255, 0.12)" />
  </div>
  <div class="absolute bottom-0 right-0 w-16 h-16 pointer-events-none" style="z-index: 1">
    <div class="absolute bottom-4 right-4 w-8 h-px" style="background: rgba(255, 255, 255, 0.12)" />
    <div class="absolute bottom-4 right-4 w-px h-8" style="background: rgba(255, 255, 255, 0.12)" />
  </div>

  <!-- Footer -->
  <div
    v-if="$nav.currentPage !== 1 && $nav.currentPage !== $nav.total"
    class="absolute bottom-0 left-0 right-0 flex items-center justify-between px-8 py-3"
    style="font-size: 0.6rem; color: rgba(255,255,255,0.25); z-index: 2"
  >
    <span style="letter-spacing: 0.1em; text-transform: uppercase">権代颯士 — 下半期成果発表</span>
    <span style="font-variant-numeric: tabular-nums">{{ String($nav.currentPage).padStart(2, '0') }} / {{ String($nav.total).padStart(2, '0') }}</span>
  </div>
</template>
