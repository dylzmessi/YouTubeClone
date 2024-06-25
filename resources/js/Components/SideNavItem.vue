<template>
    <li :class="!openSideNav ? 'py-3 px-4 w-[60px]' : 'flex items-center py-3 px-4 w-full'"
        class="text-sm text-black transition ease-in-out active:bg-gray-300 hover:bg-gray-200 rounded-lg cursor-pointer">
        <div :class="!openSideNav ? 'w-full flex justify-start' : ''">
            <component :is="icon"></component>
        </div>
        <div :class="!openSideNav ? 'text-xs mt-1 justify-center' : 'ml-4 text-sm'">
            <span v-if="!openSideNav && iconString !== 'Shorts'">{{ iconString.substring(0, 2) }}</span>
            <span v-else>{{ iconString }}</span>
        </div>
    </li>
</template>

<script setup>
import { defineProps, toRefs } from 'vue'

import Home from "vue-material-design-icons/Home.vue";
import MovieOpenPlayOutline from "vue-material-design-icons/MovieOpenPlayOutline.vue";
import MovieFilterOutline from "vue-material-design-icons/MovieFilterOutline.vue";
import AccountMultipleOutline from "vue-material-design-icons/AccountMultipleOutline.vue";
import History from "vue-material-design-icons/History.vue";
import PlaylistPlay from "vue-material-design-icons/PlaylistPlay.vue";
import MoviePlayOutline from "vue-material-design-icons/MoviePlayOutline.vue";
import ClockOutline from "vue-material-design-icons/ClockOutline.vue";
import ThumbUpOutline from "vue-material-design-icons/ThumbUpOutline.vue";

import Fire from "vue-material-design-icons/Fire.vue";
import MusicCircleOutline from "vue-material-design-icons/MusicCircleOutline.vue";
import MovieOpenOutline from "vue-material-design-icons/MovieOpenOutline.vue";
import AccessPoint from "vue-material-design-icons/AccessPoint.vue";
import GamepadVariantOutline from "vue-material-design-icons/GamepadVariantOutline.vue";
import ShoeSneaker from "vue-material-design-icons/ShoeSneaker.vue";
import Food from "vue-material-design-icons/Food.vue";
import FaceWomanShimmer from "vue-material-design-icons/FaceWomanShimmer.vue";

import Cog from "vue-material-design-icons/Cog.vue";
import Alert from "vue-material-design-icons/Alert.vue";
import HelpCircleOutline from "vue-material-design-icons/HelpCircleOutline.vue";
import SendCircleOutline from "vue-material-design-icons/SendCircleOutline.vue";


const props = defineProps({
    openSideNav: Boolean,
    iconString: String
})

const { openSideNav, iconString } = toRefs(props)

let icon = null
if (iconString.value === '首页') icon = Home
if (iconString.value === 'Shorts') icon = MovieOpenPlayOutline
if (iconString.value === '订阅') icon = MovieFilterOutline

if (iconString.value === '我的频道') icon = AccountMultipleOutline
if (iconString.value === '历史记录') icon = History
if (iconString.value === '播放列表') icon = PlaylistPlay
if (iconString.value === '我的视频') icon = MoviePlayOutline
if (iconString.value === '稍后观看') icon = ClockOutline
if (iconString.value === '赞过的视频') icon = ThumbUpOutline

if (iconString.value === '时下流行') icon = Fire
if (iconString.value === '音乐') icon = MusicCircleOutline
if (iconString.value === '电影') icon = MovieOpenOutline
if (iconString.value === '直播') icon = AccessPoint
if (iconString.value === '游戏') icon = GamepadVariantOutline
if (iconString.value === '体育') icon = ShoeSneaker
if (iconString.value === '美食') icon = Food
if (iconString.value === '时尚和美妆') icon = FaceWomanShimmer

if (iconString.value === '设置') icon = Cog
if (iconString.value === '举报记录') icon = Alert
if (iconString.value === '帮助') icon = HelpCircleOutline
if (iconString.value === '反馈') icon = SendCircleOutline

</script>