<script lang="ts">

</script>

<main class="bg-gray-100 shadow-md hover:shadow-xl w-[25vw] relative h-[55vh]">
    <h1 class="font-handwriting text-3xl font-semibold bg-orange-500 px-3 py-5 text-white">
        <slot name="title">
            <span class="text-gray-700">undefined</span>
        </slot>
    </h1>
    <div class="px-5 py-9">
        <slot name="description">
            
        </slot>
    </div>
    <a href="/about" class="bg-navbar-button bg-cover bg-right-bottom px-3 py-2 text-white font-handwriting absolute bottom-0 right-0">Go to blog</a>
</main>

<style>

</style>