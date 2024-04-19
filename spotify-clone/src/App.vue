<script setup>
import { ref, onMounted } from 'vue'
import { RouterLink, RouterView } from 'vue-router'

import ChevronUp from 'vue-material-design-icons/ChevronUp.vue'
import ChevronDown from 'vue-material-design-icons/ChevronDown.vue'
import ChevronLeft from 'vue-material-design-icons/ChevronLeft.vue'
import ChevronRight from 'vue-material-design-icons/ChevronRight.vue'

import MenuItem from './components/MenuItem.vue'
import MusicPlayer from './components/MusicPlayer.vue'

import { useSongStore } from './stores/song'
import { storeToRefs } from 'pinia'
const useSong = useSongStore()
const { isPlaying, currentTrack } = storeToRefs(useSong)

onMounted(() => {
  isPlaying.value = false
})

let openMenu = ref(false)
</script>

<template>
  <div>
    <div
      class="w-[calc(100%-240px)] h-[60px] fixed right-0 z-20 bg-[#101010] bg-opacity-80 flex items-center justify-between"
    >
      <div class="flex items-center ml-6">
        <button
          type="button"
          class="rounded-full bg-black p-[1px] cursor-pointer"
        >
          <ChevronLeft fillColor="#ffffff" :size="30" />
        </button>

        <button
          type="button"
          class="rounded-full bg-black p-[1px] ml-4 cursor-pointer"
        >
          <ChevronRight fillColor="#ffffff" :size="30" />
        </button>
      </div>

      <button
        @click="openMenu = !openMenu"
        :class="openMenu ? 'bg-[#282828]' : 'bg-black'"
        class="bg-black hover:bg-[#282828] rounded-full p-0.5 mr-8 mt-0.5 cursor-pointer"
      >
        <div class="flex items-center">
          <img
            class="rounded-full"
            width="27"
            src="https://picsum.photos/seed/200/200?grayscale"
          />
          <div class="text-white text-[14px] ml-1.5 font-semibold">
            Ross Geller
          </div>

          <ChevronDown
            v-if="!openMenu"
            @click="openMenu = true"
            fillColor="#ffffff"
            :size="25"
          />

          <ChevronUp
            v-else
            @click="openMenu = false"
            fillColor="#ffffff"
            :size="25"
          />
        </div>
      </button>

      <span
        v-if="openMenu"
        class="fixed w-[190px] bg-[#282828] shadow-2xl z-50 rounded-sm top-[52px] right-[35px] p-1 cursor-pointer"
      >
        <ul class="text-gray-200 font-semibold text-[14px]">
          <li class="px-3 py-2.5 hover:bg-[#3e3d3d] border-b border-b-gray-600">
            Profile
          </li>
          <li class="px-3 py-2.5 hover:bg-[#3e3d3d]">Log Out</li>
        </ul>
      </span>
    </div>
    <div id="Sidenav" class="h-[100%] p-6 w-[240px] fixed z-50 bg-black">
      <router-link to="/">
        <img width="125" src="/images/logo.png" />
      </router-link>
      <div class="my-8"></div>
      <ul>
        <router-link to="/">
          <menu-item
            class="ml-[1px]"
            :icon-size="18"
            name="Home"
            icon-string="home"
            page-url="/"
          />
        </router-link>
        <router-link to="/search">
          <menu-item
            class="ml-[1px]"
            :icon-size="19"
            name="Search"
            icon-string="search"
            page-url="/search"
          />
        </router-link>
        <router-link to="/library">
          <menu-item
            class="ml-[2px]"
            :icon-size="18"
            name="Library"
            icon-string="library"
            page-url="/library"
          />
        </router-link>
        <div class="py-3.5"></div>
        <menu-item
          :icon-size="20"
          name="Create Playlist"
          icon-string="playlist"
          page-url="/playlist"
        />
        <menu-item
          class="-ml-[1px]"
          :icon-size="22"
          name="Liked Songs"
          icon-string="liked"
          page-url="/liked"
        />
      </ul>
      <div class="border-b border-b-gray-700"></div>
      <ul>
        <li
          class="font-semibold text-[13px] mt-3 text-gray-300 hover:text-white"
        >
          My Playlist #1
        </li>
        <li
          class="font-semibold text-[13px] mt-3 text-gray-300 hover:text-white"
        >
          My Playlist #2
        </li>
        <li
          class="font-semibold text-[13px] mt-3 text-gray-300 hover:text-white"
        >
          My Playlist #3
        </li>
        <li
          class="font-semibold text-[13px] mt-3 text-gray-300 hover:text-white"
        >
          My Playlist #4
        </li>
      </ul>
    </div>
    <div
      class="fixed right-0 top-0 w-[calc(100%-240px)] overflow-auto h-full bg-gradient-to-b from-[#1c1c1c] to-black"
    >
      <div class="mt-[70px]"></div>
      <router-view />
      <div class="mb-[100px]"></div>
    </div>
    <music-player v-if="currentTrack" />
  </div>
</template>
