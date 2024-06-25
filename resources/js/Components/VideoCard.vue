<template>
  <div class="relative">
    <div class="rounded-lg bg-white m-2"
      :class="[show ? 'absolute z-30 transition ease-in-out delay-150 duration-300 hover:translate-y-8 hover:scale-125' : '']">
      <div @mouseover="show = true" @mouseleave="show = false; showVideo = false;">
        <img class="aspect-video cursor-pointer" :src="thumbnail || ''"
          :class="show ? 'transition ease-in-out delay-150 rounded-l-lg' : 'rounded-lg', showVideo ? 'delay-300 hidden' : ''" />
        <div class="w-full h-full aspect-video cursor-pointer" :class="showVideo ? '' : 'delay-300 hidden'">
          <video ref="video" :src="videoUrl || ''" type="video/mp4"></video>
        </div>
      </div>
      <div>
        <div class="mt-2 flex justify-start items-start space-x-4">
          <div>
            <img class="rounded-full w-10" :src="image || ''" />
          </div>
          <div class="space-y-1">
            <div class="font-medium text-[16px] w-full cursor-pointer line-clamp-2 leading-5">{{ title.substring(0,
              100) }}</div>
            <div class="font-normal text-xs w-full cursor-pointer flex gap-1 line-clamp-1 items-center text-gray-600">{{
              user.substring(0, 30) }}
              <CheckCircle fillColor="#888" :size="16" />
            </div>
            <div class="font-normal text-xs w-full cursor-pointer flex gap-1 items-center line-clamp-1 text-gray-600">{{
              views }}</div>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script setup>
import { defineProps, toRefs, ref, watch, onMounted } from "vue";

import CheckCircle from "vue-material-design-icons/CheckCircle.vue";

const props = defineProps({
  title: String,
  user: String,
  views: String,
  image: String,
  videoUrl: String,
  thumbnail: String,
});

const { title, user, views, image, videoUrl, thumbnail } = toRefs(props);

let show = ref(false);
let showVideo = ref(false);
let video = ref(null);
let width = ref(document.documentElement.clientWidth)

onMounted(() => {
  window.addEventListener('resize', () => {
    width.value = document.documentElement.clientWidth;
  })
})

watch(
  () => show.value,
  (show) => {
    if (show) {
      showVideo.value = true;
      video.value.play();
      return "";
    }
    showVideo.value = false;
    video.value.pause();
    video.value.currentTime = 0;
  }
);
</script>
