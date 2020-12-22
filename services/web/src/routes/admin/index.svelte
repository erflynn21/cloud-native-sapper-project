<script>
    import { goto } from "@sapper/app";
    import { onMount } from "svelte";
    import { currentUser } from "../../stores/user";

    onMount(() => {
        if (!$currentUser) {
            goto("/auth/login?redirect=admin");
        }
    });
</script>

{#if $currentUser}
    <h1>Admin Dashboard</h1>
    <p>Only authenticated users have access to this</p>
{/if}
