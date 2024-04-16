<script setup>
import HomeCard from '../components/HomeCard.vue'
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
      <div class="flex items-center">
        <home-card
          image="https://picsum.photos/seed/9/200/200"
          title="Title is here"
          sub-title="Subtitle is here"
        />

        <home-card
          class="sm:block hidden"
          image="https://picsum.photos/seed/45/200/200"
          title="Title is here 2"
          sub-title="Subtitle is here 2"
        />

        <home-card
          class="md:block hidden"
          image="https://picsum.photos/seed/3/200/200"
          title="Title is here 3"
          sub-title="Subtitle is here 3"
        />
        <home-card
          class="lg:block hidden"
          image="https://picsum.photos/seed/40/200/200"
          title="Title is here 4"
          sub-title="Subtitle is here 4"
        />

        <home-card
          class="xl:block hidden"
          image="https://picsum.photos/seed/5/200/200"
          title="Title is here 5"
          sub-title="Subtitle is here 5"
        />
      </div>
    </div>
    <div class="p-8">
      <button
        type="button"
        class="text-white text-2xl font-semibold hover:underline cursor-pointer"
      >
        Recommended Songs
      </button>

      <div class="py-2"></div>
      <div class="flex items-center">
        <home-card
          image="https://picsum.photos/seed/100/200/200"
          title="Title is here 6"
          sub-title="Subtitle is here 6"
        />

        <home-card
          class="sm:block hidden"
          image="https://picsum.photos/seed/60/200/200"
          title="Title is here 7"
          sub-title="Subtitle is here 7"
        />

        <home-card
          class="md:block hidden"
          image="https://picsum.photos/seed/50/200/200"
          title="Title is here 8"
          sub-title="Subtitle is here 8"
        />
        <home-card
          class="lg:block hidden"
          image="https://picsum.photos/seed/70/200/200"
          title="Title is here 9"
          sub-title="Subtitle is here 9"
        />

        <home-card
          class="xl:block hidden"
          image="https://picsum.photos/seed/80/200/200"
          title="Title is here 10"
          sub-title="Subtitle is here 10"
        />
      </div>
    </div>
  </div>
</template>
