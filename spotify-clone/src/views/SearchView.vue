<script setup>
import CategorySelect from '../components/CategorySelect.vue'
</script>
<template>
  <div>
    <div class="p-8">
      <button
        type="button"
        class="text-white text-2xl font-semibold hover:underline cursor-pointer"
      >
        Podcasts to make you happy
      </button>

      <div class="py-2"></div>
      <div
        class="grid xl:grid-cols-5 lg:grid-cols-4 md:grid-cols-3 sm:grid-cols-2 gap-6"
      >
        <category-select
          category="Podcasts"
          image="https://picsum.photos/seed/109/200/200"
        />
        <category-select
          category="Audiobooks"
          image="https://picsum.photos/seed/108/200/200"
        />
        <category-select
          category="Songs"
          image="https://picsum.photos/seed/107/200/200"
        />
        <category-select
          category="New Releases"
          image="https://picsum.photos/seed/113/200/200"
        />
        <category-select
          category="Podcasts"
          image="https://picsum.photos/seed/105/200/200"
        />
        <category-select
          category="Audiobooks"
          image="https://picsum.photos/seed/104/200/200"
        />
        <category-select
          category="Songs"
          image="https://picsum.photos/seed/103/200/200"
        />
        <category-select
          category="New Releases"
          image="https://picsum.photos/seed/102/200/200"
        />
        <category-select
          category="Podcasts"
          image="https://picsum.photos/seed/101/200/200"
        />
        <category-select
          category="Audiobooks"
          image="https://picsum.photos/seed/110/200/200"
        />
        <category-select
          category="Songs"
          image="https://picsum.photos/seed/111/200/200"
        />
        <category-select
          category="New Releases"
          image="https://picsum.photos/seed/112/200/200"
        />
      </div>
    </div>
  </div>
</template>
