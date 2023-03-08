<script>
    import { page } from "$app/stores";
    import { base } from "$app/paths";
</script>

<main>
    <span>~{$page.route.id}</span>
    <nav>
        <a class="link" href="{base}/">/Home</a>
        <a class="link" href="{base}/about">/About</a>
    </nav>
</main>
