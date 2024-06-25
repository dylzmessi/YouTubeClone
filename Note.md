## Full Stack YouTube Clone (Vue JS, Javascript, Tailwind CSS, Laravel, Inertia JS, PHP)

# 1、https://laravel.com/docs/11.x
安装laravel_v11(需要php8.2,composer2.5)
composer create-project laravel/laravel YouTubeClone

# 2、https://laravel.com/docs/11.x/starter-kits#laravel-breeze
安装laravel-breeze身份验证套件
composer require laravel/breeze --dev
支持服务端渲染ssr
php artisan breeze:install vue --ssr 

# 3、
前端构建
npm i
npm run dev

# 4、https://tailwindcss.com/docs/guides/vite#vue
导入tailwindcss
npm install -D tailwindcss postcss autoprefixer
npx tailwindcss init -p

# 5、
导入图标
npm install vue-material-design-icons
导入Vue3轮播插件
npm install vue3-carousel
导入滚动条Simplebar插件
npm install simplebar-vue --save
import Simplebar from 'simplebar-vue';
import 'simplebar-vue/dist/simplebar.min.css';






