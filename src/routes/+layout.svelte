<script type="ts">
    import '../style.css'
    import NavBar from '../components/NavBar.svelte';
</script>

<div class="Layout">
    <NavBar></NavBar>
    <main>
        <slot />
    </main>
</div>