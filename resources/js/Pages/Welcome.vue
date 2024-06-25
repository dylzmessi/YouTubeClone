<script setup>
import { Head, Link } from "@inertiajs/vue3";
import NavLayout from "@/Layouts/NavLayout.vue";
import VideoCard from "@/Components/VideoCard.vue";

/* defineProps({
    canLogin: {
        type: Boolean,
    },
}); */
</script>

<template>

    <Head title="YouTube" />
    <NavLayout>
        <div class="grid 2xl:grid-cols-5 xl:grid-cols-4 lg:grid-cols-3 md:grid-cols-3 sm:grid-cols-2">
            <VideoCard 
            title="这只猫在等主人回家 ❤️" 
            user="阿威" 
            views="9846次观看·三天前" 
            image="/images/02.jpg" 
            videoUrl="/videos/cat.mp4" 
            thumbnail="/videos/Thumbnails/cat.jpg" />
        </div>
    </NavLayout>
</template>
