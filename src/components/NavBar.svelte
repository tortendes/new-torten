<script lang="ts">
    import { afterUpdate } from 'svelte';
    let toggle: boolean;

    const toggleNavbar = (): boolean => {
        return toggle = !toggle
    }

    let navbar: number;
    let sticky: boolean;
    let scrollY: number;

    afterUpdate(() => {
        if (50 >= scrollY) {
            sticky = false
            console.log(sticky)
        } else {
            sticky = true
            console.log(sticky)
        }
    })
</script>

<nav>
    {#if toggle}
    <div class="navigation {toggle ? "opacity-100 visible" : "opacity-0 hidden"} transition-opacity ease-in duration-300">
        <div class="main-content">
            <div class="flex flex-col justify-center">
                <ul class="main mt-20">
                    <li>
                        <a href="/about">About</a>
                    </li>
                    <li>
                        <a href="https://blog.torten.xyz">Blog</a>
                    </li>
                    <li>
                        <a href="/projects">Projects</a>
                    </li>
                    <li class="mt-2">
                        <a href="https://tortenworx.xyz">tortenworx</a>
                    </li>

                </ul>
                <ul class="mt-5">
                    <li class="flex flex-col justify-center text-white font-light">
                        <a href="/contact">Contact</a>
                        <a href="https://tortenworx.xyz/legal/torten/privacy">Privacy Policy</a>
                        <a href="https://tortenworx.xyz/legal/torten/eula">EULA</a>

                    </li>
                </ul>
                <div class="mt-4">
                    <span class="text-white font-thin text-sm">&copy; Torten Webworks Opc</span>
                </div>
            </div>
        </div>
        <div class="bg-navbar-button bg-cover md:w-1/2 w-full h-screen">

        </div>
    </div>
    {/if}
    <div class="w-full flex items-center justify-between {toggle ? 'bg-transparent': 'bg-zinc-800'} transition ease-in duration-300 fixed">
        <div class="px-3 py-2 relative">
            <img src="/trtn-static/whole-monochrome-white.svg" alt="torten logo">
        </div>
        <button on:click={toggleNavbar} class="{toggle ? 'bg-transparent': 'bg-navbar-button'} flex flex-col items-center justify-center gap-1 w-14 h-14 bg-cover ml-auto relative">
            <span class="w-5 h-0.5 bg-white {toggle ? 'absolute top-[50%] origin-center rotate-45 transition-transform ease-in-out' : ''}"></span>
            <span class="w-5 h-0.5 bg-white {toggle ? 'absolute top-[50%] origin-center -rotate-45 transition-transform ease-in-out' : ''}"></span>
        </button>
    </div>
</nav>

<style>
    .navigation .main-content {
        @apply fixed bg-zinc-800 md:w-1/2 h-full md:visible invisible px-10 py-2; 
    }
    .navigation {
        @apply fixed top-0 left-0 w-full h-screen flex;
    }
    .navigation .main-content ul.main {
        @apply flex flex-col justify-center gap-3;
    }
    .navigation .main-content ul.main a {
        @apply text-white text-3xl font-medium
    }
</style>
<svelte:window bind:scrollY={scrollY} />