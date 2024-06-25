<script setup>
import { ref } from "vue";
import { Link } from "@inertiajs/vue3";
import SideNavItem from '@/Components/SideNavItem.vue'

import MenuIcon from "vue-material-design-icons/Menu.vue";
import MagnifyIcon from "vue-material-design-icons/Magnify.vue";
import MovieOpenPlusOutlineIcon from "vue-material-design-icons/MovieOpenPlusOutline.vue";
import BellIcon from "vue-material-design-icons/Bell.vue";

import Simplebar from 'simplebar-vue';
import 'simplebar-vue/dist/simplebar.min.css';

let openSideNav = ref(true)
</script>

<template>
    <div class="relative">
        <div id="TopNav" class="h-[60px] w-full fixed z-20 flex justify-between items-center bg-white px-2">
            <div class="flex justify-start">
                <button @click="openSideNav = !openSideNav"
                    class="inline-block p-2 ml-2 rounded-full cursor-pointer transition ease-in-out hover:bg-gray-200 active:bg-gray-300">
                    <MenuIcon fillColor="#000" :size="24" />
                </button>
                <div class="mx-2"></div>
                <div class="flex justify-center items-center mr-10 cursor-pointer">
                    YouTube
                </div>
            </div>
            <div class="md:w-[400px] lg:w-[600px] hidden md:block">
                <div class="bg-white flex items-center rounded-full border border-gray-300">
                    <input type="text" placeholder="搜索"
                        class="form-control w-full block px-5 py-2 text-base font-normal placeholder-gray-400 bg-clip-padding border-y-transparent border-l-transparent border-r-gray-300 rounded-l-full transition ease-in-out m-0 border-transparent focus:ring-0">
                    <MagnifyIcon fillColor="#000" :size="26" class="mx-4 cursor-pointer" />
                </div>
            </div>
            <div class="flex items-center justify-between">
                <button
                    class="inline-block p-2 ml-2 rounded-full cursor-pointer hover:bg-gray-200 active:bg-gray-300 transition ease-in-out">
                    <MovieOpenPlusOutlineIcon fillColor="#000" :size="24" />
                </button>
                <button
                    class="inline-block p-2 ml-2 rounded-full cursor-pointer hover:bg-gray-200 active:bg-gray-300 transition ease-in-out">
                    <BellIcon fillColor="#000" :size="24" class="font-thin" />
                </button>
                <img class="rounded-full mx-8" width="36" src="/images/01.jpg" alt="">
            </div>
        </div>

        <div id="SideNav" class="h-full fixed z-0 bg-white w-[240px]" :class="[!openSideNav ? 'w-fit' : 'w-[240px]']">
            <ul class="mt-[60px] h-full px-2 w-full">
                <Simplebar data-simplebar-auto-hide="true" class="pr-4" style="max-height: calc(100% - 60px);">
                    <SideNavItem :openSideNav="openSideNav" iconString="首页" />
                    <SideNavItem :openSideNav="openSideNav" iconString="Shorts" />
                    <SideNavItem :openSideNav="openSideNav" iconString="订阅" />
                    <SideNavItem v-if="!openSideNav" :openSideNav="openSideNav" iconString="我的视频" />
                    <div v-else>
                        <div class="border-b border-b-gray-200 my-3"></div>
                        <li
                            class="p-2 ml-1 cursor-pointer hover:bg-gray-200 active:bg-gray-300 rounded-lg transition ease-in-out">
                            <span>我 ></span>
                        </li>
                        <SideNavItem :openSideNav="openSideNav" iconString="我的频道" />
                        <SideNavItem :openSideNav="openSideNav" iconString="历史记录" />
                        <SideNavItem :openSideNav="openSideNav" iconString="播放列表" />
                        <SideNavItem :openSideNav="openSideNav" iconString="我的视频" />
                        <SideNavItem :openSideNav="openSideNav" iconString="稍后观看" />
                        <SideNavItem :openSideNav="openSideNav" iconString="赞过的视频" />
                        <div class="border-b border-b-gray-200 my-3"></div>
                        <li class="p-2 ml-1"><span>订阅</span></li>
                        <SideNavItem :openSideNav="openSideNav" iconString="我的频道" />
                        <SideNavItem :openSideNav="openSideNav" iconString="我的频道" />
                        <SideNavItem :openSideNav="openSideNav" iconString="我的频道" />
                        <div class="border-b border-b-gray-200 my-3"></div>
                        <li class="p-2 ml-1"><span>探索</span></li>
                        <SideNavItem :openSideNav="openSideNav" iconString="时下流行" />
                        <SideNavItem :openSideNav="openSideNav" iconString="音乐" />
                        <SideNavItem :openSideNav="openSideNav" iconString="电影" />
                        <SideNavItem :openSideNav="openSideNav" iconString="直播" />
                        <SideNavItem :openSideNav="openSideNav" iconString="游戏" />
                        <SideNavItem :openSideNav="openSideNav" iconString="体育" />
                        <SideNavItem :openSideNav="openSideNav" iconString="美食" />
                        <SideNavItem :openSideNav="openSideNav" iconString="时尚和美妆" />
                        <div class="border-b border-b-gray-200 my-3"></div>
                        <SideNavItem :openSideNav="openSideNav" iconString="设置" />
                        <SideNavItem :openSideNav="openSideNav" iconString="举报记录" />
                        <SideNavItem :openSideNav="openSideNav" iconString="帮助" />
                        <SideNavItem :openSideNav="openSideNav" iconString="反馈" />
                        <div class="my-2 space-y-2 text-[13px] font-normal text-gray-500">
                            <p class="px-4">About Press Copyright Contact us Creators Advertise Developers</p>
                            <p class="px-4">Terms Privacy Policy & Safety How YouTube works Test new features</p>
                        </div>
                    </div>
                </Simplebar>
            </ul>
        </div>
        <div id="SideNavOverlay"></div>
        <div :class="{ 'w-[calc(100%-70px)]': !openSideNav, 'w-[calc(100%-250px)]': openSideNav }"
            class="h-[calc(100%-60px)] absolute right-0 top-[60px]">
            <div>
                <div class="group mb-4 mx-2 flex flex-wrap space-x-4">
                    <a href="" class=''>全部</a>
                    <a href="" class=''>风景</a>
                    <a href="" class=''>游戏</a>
                    <a href="" class=''>音乐</a>
                    <a href="" class=''>旅游</a>
                    <a href="" class=''>直播</a>
                    <a href="" class=''>美食</a>
                    <a href="" class=''>动画</a>
                    <a href="" class=''>最近上传</a>
                    <a href="" class=''>发现新视频</a>
                </div>
            </div>
            <slot></slot>
        </div>
    </div>
</template>
