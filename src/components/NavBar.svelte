<script lang="ts">
    import '../styles/NavBar.scss'
    let isOpen:boolean;

    function toggleNavigation(): void {
        isOpen = !isOpen
    }
</script>
 
<header class="navigation-bar">
    <div class="image-wrapper">
        <img src="/trtn-static/whole-color.svg" alt="Torten Logo">
    </div>
    <button class="toggle-button" on:click={toggleNavigation}>
        <span></span>
        <span></span>
        <span class="sr-only">Open Navigation</span>
    </button>
</header>
<div class="navigation-menu {isOpen ? "open" : ""}">
    <div class="wrapper">
        <div class="pc-left">
            <div class="image-wrapper">
                <img src="/trtn-static/whole-color.svg" alt="Torten Logo" class="mb-20">
            </div>
            <ul class="main-links">
                <li>
                    <a href="/about">About</a>
                </li>
                <li>
                    <a href="/blog">Blog</a>
                </li>
                <li class="my-2"></li>
                <li>
                    <a href="/projects">Projects</a>
                </li>
                <li>
                    <a href="/contact">Contact</a>
                </li>
            </ul>
            <ul class="secondary-links">
                <li>
                    <a href="/legal/tos">Project's ToS</a>
                </li>
                <li>
                    <a href="/legal/privacy">Project Privacy Policy</a>
                </li>
                <li>
                    <a href="https://tortenworx.xyz">tortenworx</a>
                </li>
            </ul>
            <small class="absolute bottom-5 left-9">&copy; 2022 Torten Opc</small>
        </div>
        <div class="right">
            <button class="close" on:click={toggleNavigation}>
                <span class="sr-only">Close Navigation</span>
            </button>
        </div>
    </div>
</div>
